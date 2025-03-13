public String getReferenceData() {
        StringBuilder referenceData = new StringBuilder();
        referenceData.append("''' derivedFields\\\":[" +
                        "\\n\" +\n" +
                        "                        \"      {\\n\" +\n" +
                        "                        \"         \\\"derivedField\\\":\\\"'coveragePopulation'\\\",\\n\" +\n" +
                        "                        \"         \\\"derivedEffectiveDate\\\":\\\"\\\",\\n\" +\n" +
                        "                        \"         \\\"derivedExpirationDate\\\":\\\"\\\",\\n\" +\n" +
                        "                        \"         \\\"coTypes\\\":['MD','DN']\\n\" +\n" +
                        "                        \"      },\\n\" +\n" +
                        "                        \"      {\\n\" +\n" +
                        "                        \"         \\\"derivedField\\\":\\\"'billGroup'\\\",\\n\" +\n" +
                        "                        \"         \\\"derivedEffectiveDate\\\":\\\"\\\",\\n\" +\n" +
                        "                        \"         \\\"derivedExpirationDate\\\":\\\"\\\",\\n\" +\n" +
                        "                        \"         \\\"coTypes\\\":['MD','VS']\\n\" +\n" +
                        "                        \"         ]\\n\" +\n" +
                        "                        \"      }\\n\" +\n" +
                        "                        \"   ]\\n\" +{\n" +

                        "   \"memGroupID\":\"1318990\",\n" +
                        "   \"shouldSupply\":{\n" +
                        "      \"benefitEffectiveDate\":\"01/01/2025\",\n" +
                        "      \"employBeginDate\":\"01/01/2025\",\n" +
                        "      \"benefitStatus\":\"A\",\n" +
                        "      \"planData\":[\n" +
                        "         {\n" +
                        "            \"bundleOptionID\":\"12349\",\n" +
                        "            \"coverageOptionType\":\"MD\",\n" +
                        "            \"billGroups\":[\n" +
                        "               \"11\",\n" +
                        "               \"22\"\n" +
                        "            ],\n" +
                        "            \"ediEnrollmentIDs\":[\n" +
                        "               \"SG01CLO1\",\n" +
                        "               \"SG01CL02\",\n" +
                        "               \"SG02CL01\",\n" +
                        "               \"SG02CL02\"\n" +
                        "            ],\n" +
                        "            \"coveragePopulations\":[\n" +
                        "               \"1111\",\n" +
                        "               \"2222\"\n" +
                        "            ],\n" +
                        "            \"customAttributes\":[\n" +
                        "               {\n" +
                        "                  \"customAttributeName\":\"Location\",\n" +
                        "                  \"customAttributesValues\":[\n" +
                        "                     \"MN\",\n" +
                        "                     \"BOS\"\n" +
                        "                  ]\n" +
                        "               },\n" +
                        "               {\n" +
                        "                  \"customAttributeName\":\"CovType\",\n" +
                        "                  \"customAttributesValues\":[\n" +
                        "                     \"ACT\",\n" +
                        "                     \"COB\"\n" +
                        "                  ]\n" +
                        "               }\n" +
                        "            ]\n" +
                        "         },\n" +
                        "         {\n" +
                        "            \"bundleOptionID\":\"56789\",\n" +
                        "            \"coverageOptionType\":\"DN\",\n" +
                        "            \"billGroups\":[\n" +
                        "               \"33\",\n" +
                        "               \"44\"\n" +
                        "            ],\n" +
                        "            \"ediEnrollmentIDs\":[\n" +
                        "               \"SG03CLO1\",\n" +
                        "               \"SG03CL02\",\n" +
                        "               \"SG04CLO1\",\n" +
                        "               \"SG04CL02\"\n" +
                        "            ],\n" +
                        "            \"coveragePopulations\":[\n" +
                        "               \"4444\",\n" +
                        "               \"5555\"\n" +
                        "            ],\n" +
                        "            \"customAttributes\":[\n" +
                        "               {\n" +
                        "                  \"customAttributeName\":\"Location\",\n" +
                        "                  \"customAttributesValues\":[\n" +
                        "                     \"NY\",\n" +
                        "                     \"NJ\"\n" +
                        "                  ]\n" +
                        "               },\n" +
                        "               {\n" +
                        "                  \"customAttributeName\":\"CovType\",\n" +
                        "                  \"customAttributesValues\":[\n" +
                        "                     \"ACT\",\n" +
                        "                     \"COB\"\n" +
                        "                  ]\n" +
                        "               }\n" +
                        "            ]\n" +
                        "         }\n" +
                        "      ]\n" +
                        "   },\n"
                )
                .append(" '''")
                .append("\n");
        return referenceData.toString();
    }



public String getCsvHeader() {
        StringBuilder csv = new StringBuilder();
        csv.append("memberGroupID,").append("affiliationExternalID,").append("relationshipCode,")
                .append("firstName,").append("lastName,")
                .append("birthDate,").append("gender,")
                .append("addressType,").append("address1,").append("city,").append("state,").append("postalCode,")
                .append("country,").append("communicationType,").append("communicationText,").append("externalIDType,")
                .append("employBeginDate,").append("employStatusCode,").append("benefitEffectiveDate,").append("qualifyingEvent,")
                .append("qualifyingEventDate,").append("MD_CoverageOptionID,").append("DN_CoverageOptionID,").append("VS_CoverageOptionID,")
                .append("MD_coveragePopulationID,").append("DN_coveragePopulationID,").append("VS_coveragePopulationID,")
                .append("MD_BillGroupReferenceID,") .append("DN_BillGroupReferenceID,") .append("VS_BillGroupReferenceID,");
        return csv.toString();
    }

    public String getInstructions() {
        StringBuilder instructionsCsv = new StringBuilder();
        instructionsCsv.append("### **Instructions for Generating Synthetic Data**\n\n")
                .append("1. **Fetch Members:**\n")
                .append("   1.1 Extract the requested number of members from the user query.\n")
                .append("   1.2 Each member represents a family.\n")
                .append("   1.3 Each family consists of 1 to 3 individuals.\n\n")
                .append("2. **Individual Representation:**\n")
                .append("   2.1 Each row represents an individual belonging to a family.\n")
                .append("   2.2 Assign the `memberGroupID` from the user query to each individual.\n\n")
                .append("3. **Generate Unique IDs:**\n")
                .append("   3.1 Generate a unique 9-digit `affiliationExternalID` for each family.\n")
                .append("   3.2 The number of unique `affiliationExternalID`s must match the number of requested members before proceeding.\n\n")
                .append("4. **Family Composition:**\n")
                .append("   4.1 Each family must contain exactly **one subscriber**.\n")
                .append("   4.2 A family **may** have one spouse and one child, but not more.\n\n")
                .append("5. **Assign Relationship Codes:**\n")
                .append("   - `18` for the **subscriber** (always present).\n")
                .append("   - `01` for the **spouse** (optional).\n")
                .append("   - `19` for the **child** (optional).\n\n")
                .append("6. **Employment Details:**\n")
                .append("   6.1 Set `employBeginDate` as to the `benefitEffectiveDate` from `referenceData` in 'yyyy-mm-dd' format.  Only for subscribers (`relationshipCode=18`), leave \"NULL\" for others.\n")
                .append("   6.2 Set `employStatusCode` as **'A'** only for subscribers, leave \"NULL\" for others.\n\n")
                .append("7. **Validation & Correction:**\n")
                .append("   7.1 Ensure the total number of `affiliationExternalID`s matches the requested families.\n")
                .append("   7.2 If validation fails, correct discrepancies before returning the CSV.\n\n")
                .append("8. **Assign Contact Details:**\n")
                .append("   8.1 Generate `firstName` and `lastName` (use any valid names).\n")
                .append("   8.2 Generate `birthDate` in 'yyyy-mm-dd' format , ensuring it does not exceed **150 years from today**.\n")
                .append("   8.3 Assign `gender`: Randomly choose from **'M', 'F', or 'U'**.\n")
                .append("   8.4 Set `addressType` to **'HOM'**.\n")
                .append("   8.5 Assign `address1`: Use a valid **USA address**.\n")
                .append("   8.6 Ensure `city`, `state`, and `postalCode` form a valid combination.\n")
                .append("   8.7 Set `country` to **'US'**.\n")
                .append("   8.8 Set `communicationType` to **'EML'**.\n")
                .append("   8.9 Generate `communicationText` as an email in **firstname_lastname@test.com** format.\n")
                .append("   8.10 Set `externalIDType` to **'0F'**.\n\n")
                .append("9. **Benefit Details:**\n")
                .append("   9.1 Use `benefitEffectiveDate` from `referenceData` in 'yyyy-mm-dd' format.\n")
                .append("   9.2 Set `qualifyingEvent` to **'28'**.\n")
                .append("   9.3 Set `qualifyingEventDate` to the `benefitEffectiveDate` from `referenceData` in 'yyyy-mm-dd' format.\n\n")
                .append("10. **Coverage Data Assignment:**\n")
                .append("   10.1 **MD_CoverageOptionID**: Extract `bundleOptionID` where `coverageOptionType='MD'` from `referenceData.planData`. If not found, then explicitly set `MD_CoverageOptionID = \"NULL\"` (do not assign any value).\n")
                .append("   10.2 **DN_CoverageOptionID**: Extract `bundleOptionID` where `coverageOptionType='DN'` from `referenceData.planData`. If not found, then explicitly set `DN_CoverageOptionID = \"NULL\"` (do not assign any value).\n")
                .append("   10.3 **VS_CoverageOptionID**: Extract `bundleOptionID` where `coverageOptionType='VS'` from `referenceData.planData`. If not found, then explicitly set `VS_CoverageOptionID = \"NULL\"` (do not assign any value).\n\n")

                .append("11. Coverage Population ID Assignment:\n")
                .append(" 11.1 Read `referenceData.derivedFields`. This is an **array of objects**, where each object has a `derivedField` key.\n")
                .append(" 11.2 Search for an object where `derivedField = \"coveragePopulation\"`.\n")
                .append(" 11.3 **If an object with `derivedField = \"coveragePopulation\"` is found:**\n")
                .append("      - Extract the `coTypes` array from that object.\n")
                .append("      - **If `coTypes` contains `MD`, then explicitly set `MD_CoveragePopulationID = \"NULL\"` (do not assign any value).**\n")
                .append("      - **If `coTypes` contains `DN`, then explicitly set `DN_CoveragePopulationID = \"NULL\"` (do not assign any value).**\n")
                .append("      - **If `coTypes` contains `VS`, then explicitly set `VS_CoveragePopulationID = \"NULL\"` (do not assign any value).**\n")
                .append(" 11.4 **Only if `derivedField = \"coveragePopulation\"` is missing OR `coTypes` does not contain the type:**\n")
                .append("      - Assign a random value from `planData.coveragePopulations` where `coverageOptionType` matches (MD, DN, VS).\n")
                .append(" 11.5 Ensure all members of the same family share the same Coverage Population ID.\n")
                .append(" 11.6 Spouse and child cannot have any value that the subscriber does not.\n")
                .append(" 11.7 **If `MD_CoveragePopulationID`, `DN_CoveragePopulationID`, or `VS_CoveragePopulationID` is already set to `\"NULL\"`, do not assign any value later.**\n\n")
                .append("12. **Bill Group Reference Assignment:**\n")
                .append("   12.1 Read `referenceData.derivedFields`. This is an **array of objects**, where each object has a `derivedField` key.\n")
                .append("   12.2 Search for an object where `derivedField = \"billGroup\"`.\n")
                .append("   12.3 **If an object with `derivedField = \"billGroup\"` is found:**\n")
                .append("       - Extract the `coTypes` array from that object.\n")
                .append("       - **If `coTypes` contains `MD`, then explicitly set `MD_BillGroupReferenceID = \"NULL\"` (do not assign any value).**\n")
                .append("       - **If `coTypes` contains `DN`, then explicitly set `DN_BillGroupReferenceID = \"NULL\"` (do not assign any value).**\n")
                .append("       - **If `coTypes` contains `VS`, then explicitly set `VS_BillGroupReferenceID = \"NULL\"` (do not assign any value).**\n")
                .append("   12.4 **Only if `derivedField = \"billGroup\"` is missing OR `coTypes` does not contain the type:**\n")
                .append("       - Assign a random value from `planData.billGroups` where `coverageOptionType` matches (MD, DN, VS).\n")
                .append("   12.5 Ensure all members of the same family share the same BillGroupReferenceID.\n")
                .append("   12.6 Spouse and child cannot have any value that the subscriber does not.\n")
                .append("### **User Query Example:**\n")
                .append("- **'Enroll 10 members'** should result in **10 families** with valid relationships and unique IDs.\n");

        return instructionsCsv.toString();
    }
