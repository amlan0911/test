StringBuilder prompt = new StringBuilder();

// Coverage Data Assignment
prompt.append("10. Coverage Data Assignment:\n")
      .append("  10.1 MD_CoverageOptionID: Extract bundleOptionID where coverageOptionType = \"MD\" from referenceData.planData.\n")
      .append("       - If no such bundleOptionID is found, explicitly set MD_CoverageOptionID = \"NULL\" (do not assign any value).\n")
      .append("  10.2 DN_CoverageOptionID: Extract bundleOptionID where coverageOptionType = \"DN\" from referenceData.planData.\n")
      .append("       - If no such bundleOptionID is found, explicitly set DN_CoverageOptionID = \"NULL\" (do not assign any value).\n")
      .append("  10.3 VS_CoverageOptionID: Extract bundleOptionID where coverageOptionType = \"VS\" from referenceData.planData.\n")
      .append("       - If no such bundleOptionID is found, explicitly set VS_CoverageOptionID = \"NULL\" (do not assign any value).\n\n");

// Coverage Population ID Assignment
prompt.append("11. Coverage Population ID Assignment:\n")
      .append("  11.1 Read referenceData.derivedFields. This is an array of objects, where each object has a `derivedField` key.\n")
      .append("  11.2 Search for an object where `derivedField` = \"coveragePopulation\" (handling both JSON key-value and raw text).\n")
      .append("  11.3 If an object with `derivedField` = \"coveragePopulation\" exists:\n")
      .append("       - Extract the `coTypes` array from that object (handling \"MD\", 'MD', MD, and similar formats).\n")
      .append("       - If `coTypes` contains \"MD\" or 'MD', explicitly set MD_CoveragePopulationID = \"NULL\".\n")
      .append("       - If `coTypes` contains \"DN\" or 'DN', explicitly set DN_CoveragePopulationID = \"NULL\".\n")
      .append("       - If `coTypes` contains \"VS\" or 'VS', explicitly set VS_CoveragePopulationID = \"NULL\".\n")
      .append("  11.4 Only if `derivedField` = \"coveragePopulation\" is missing OR `coTypes` does not contain the respective type:\n")
      .append("       - Assign a random value from planData.coveragePopulations where coverageOptionType matches the respective category (MD, DN, VS).\n")
      .append("  11.5 Ensure all members of the same family share the same Coverage Population ID.\n")
      .append("  11.6 Spouse and child cannot have any value that the subscriber does not.\n")
      .append("  11.7 Once MD_CoveragePopulationID, DN_CoveragePopulationID, or VS_CoveragePopulationID is set to \"NULL\", do not override it later.\n\n");

// Bill Group Reference ID Assignment
prompt.append("12. Bill Group Reference ID Assignment:\n")
      .append("  12.1 Read referenceData.derivedFields. This is an array of objects, where each object has a `derivedField` key.\n")
      .append("  12.2 Search for an object where `derivedField` = \"billGroup\" (handling both JSON key-value and raw text).\n")
      .append("  12.3 If an object with `derivedField` = \"billGroup\" exists:\n")
      .append("       - Extract the `coTypes` array from that object (handling \"MD\", 'MD', MD, and similar formats).\n")
      .append("       - If `coTypes` contains \"MD\" or 'MD', explicitly set MD_BillGroupReferenceID = \"NULL\".\n")
      .append("       - If `coTypes` contains \"DN\" or 'DN', explicitly set DN_BillGroupReferenceID = \"NULL\".\n")
      .append("       - If `coTypes` contains \"VS\" or 'VS', explicitly set VS_BillGroupReferenceID = \"NULL\".\n")
      .append("  12.4 Only if `derivedField` = \"billGroup\" is missing OR `coTypes` does not contain the respective type:\n")
      .append("       - Assign a random value from planData.billGroups where coverageOptionType matches the respective category (MD, DN, VS).\n")
      .append("  12.5 Ensure all members of the same family share the same Bill Group Reference ID.\n")
      .append("  12.6 Spouse and child cannot have any value that the subscriber does not.\n")
      .append("  12.7 Once MD_BillGroupReferenceID, DN_BillGroupReferenceID, or VS_BillGroupReferenceID is set to \"NULL\", do not override it later.\n");

// Print or use the prompt
System.out.println(prompt.toString());
