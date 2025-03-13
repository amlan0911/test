 .append("11. **Coverage Population ID Assignment:**\n")
                .append("   11.1 **MD_CoveragePopulationID:**\n")
                .append("       11.1.1 Parse the `referenceData` JSON.\n")
                .append("       11.1.2 Check for the `derivedFields` key (path: `referenceData.derivedFields`).\n")
                .append("       11.1.3 If `derivedField` = 'coveragePopulation' is found (path: `referenceData.derivedFields.derivedField`):\n")
                .append("           - Check the `coTypes` list for 'MD' (path: `referenceData.derivedFields.coTypes`).\n")
                .append("           - If 'MD' is found, set `MD_CoveragePopulationID` to blank.\n")
                .append("           - If 'MD' is not found, randomize a value from `coveragePopulations` in `planData` where `coverageOptionType` = 'MD' (path: `referenceData.planData.coveragePopulations`).\n")
                .append("       11.1.4 If `derivedField` = 'coveragePopulation' is not found:\n")
                .append("           - Randomize a value from `coveragePopulations` in `planData` where `coverageOptionType` = 'MD' (path: `referenceData.planData.coveragePopulations`).\n")
                .append("       11.1.5 Ensure all members of the same family have the same `MD_CoveragePopulationID`.\n")
                .append("       11.1.6 Spouse and child cannot have any value that the subscriber doesn't.\n")
                .append("       11.1.7 `MD_CoveragePopulationID` is mandatory for all individuals if there is no derived field.\n\n")
                .append("   11.2 **DN_CoveragePopulationID:**\n")
                .append("       11.2.1 Parse the `referenceData` JSON.\n")
                .append("       11.2.2 Check for the `derivedFields` key (path: `referenceData.derivedFields`).\n")
                .append("       11.2.3 If `derivedField` = 'coveragePopulation' is found (path: `referenceData.derivedFields.derivedField`):\n")
                .append("           - Check the `coTypes` list for 'DN' (path: `referenceData.derivedFields.coTypes`).\n")
                .append("           - If 'DN' is found, set `DN_CoveragePopulationID` to blank.\n")
                .append("           - If 'DN' is not found, randomize a value from `coveragePopulations` in `planData` where `coverageOptionType` = 'DN' (path: `referenceData.planData.coveragePopulations`).\n")
                .append("       11.2.4 If `derivedField` = 'coveragePopulation' is not found:\n")
                .append("           - Randomize a value from `coveragePopulations` in `planData` where `coverageOptionType` = 'DN' (path: `referenceData.planData.coveragePopulations`).\n")
                .append("       11.2.5 Ensure all members of the same family have the same `DN_CoveragePopulationID`.\n")
                .append("       11.2.6 Spouse and child cannot have any value that the subscriber doesn't.\n")
                .append("       11.2.7 `DN_CoveragePopulationID` is mandatory for all individuals if there is no derived field.\n\n")
                .append("   11.3 **VS_CoveragePopulationID:**\n")
                .append("       11.3.1 Parse the `referenceData` JSON.\n")
                .append("       11.3.2 Check for the `derivedFields` key (path: `referenceData.derivedFields`).\n")
                .append("       11.3.3 If `derivedField` = 'coveragePopulation' is found (path: `referenceData.derivedFields.derivedField`):\n")
                .append("           - Check the `coTypes` list for 'VS' (path: `referenceData.derivedFields.coTypes`).\n")
                .append("           - If 'VS' is found, set `VS_CoveragePopulationID` to blank.\n")
                .append("           - If 'VS' is not found, randomize a value from `coveragePopulations` in `planData` where `coverageOptionType` = 'VS' (path: `referenceData.planData.coveragePopulations`).\n")
                .append("       11.3.4 If `derivedField` = 'coveragePopulation' is not found:\n")
                .append("           - Randomize a value from `coveragePopulations` in `planData` where `coverageOptionType` = 'VS' (path: `referenceData.planData.coveragePopulations`).\n")
                .append("       11.3.5 Ensure all members of the same family have the same `VS_CoveragePopulationID`.\n")
                .append("       11.3.6 Spouse and child cannot have any value that the subscriber doesn't.\n")
                .append("       11.3.7 `VS_CoveragePopulationID` is mandatory for all individuals if there is no derived field.\n\n")
                .append("   11.4 **Validation Rules:**\n")
                .append("       - Ensure all members of the same family share the same `CoveragePopulationID`.\n")
                .append("       - Spouse/child cannot have values that the subscriber lacks.\n")
                .append("       - Ensure correct mapping: `MD` data should only be used for `MD_CoveragePopulationID`, `DN` for `DN_CoveragePopulationID`, and `VS` for `VS_CoveragePopulationID`.\n")
                .append("       - If no matching object is found for a coverage type, set the value to blank.\n\n")
                .append("12. **Bill Group Reference Assignment:**\n")
                .append("   12.1 **MD_BillGroupReferenceID:**\n")
                .append("       12.1.1 Parse the `referenceData` JSON.\n")
                .append("       12.1.2 Check for the `derivedFields` key (path: `referenceData.derivedFields`).\n")
                .append("       12.1.3 If `derivedField` = 'billGroup' is found (path: `referenceData.derivedFields.derivedField`):\n")
                .append("           - Check the `coTypes` list for 'MD' (path: `referenceData.derivedFields.coTypes`).\n")
                .append("           - If 'MD' is found, set `MD_BillGroupReferenceID` to blank.\n")
                .append("           - If 'MD' is not found, randomize a value from `billGroups` in `planData` where `coverageOptionType` = 'MD' (path: `referenceData.planData.billGroups`).\n")
                .append("       12.1.4 If `derivedField` = 'billGroup' is not found:\n")
                .append("           - Randomize a value from `billGroups` in `planData` where `coverageOptionType` = 'MD' (path: `referenceData.planData.billGroups`).\n")
                .append("       12.1.5 Ensure all members of the same family have the same `MD_BillGroupReferenceID`.\n")
                .append("       12.1.6 Spouse and child cannot have any value that the subscriber doesn't.\n")
                .append("       12.1.7 `MD_BillGroupReferenceID` is mandatory for all individuals if there is no derived field.\n\n")
                .append("   12.2 **DN_BillGroupReferenceID:**\n")
                .append("       12.2.1 Parse the `referenceData` JSON.\n")
                .append("       12.2.2 Check for the `derivedFields` key (path: `referenceData.derivedFields`).\n")
                .append("       12.2.3 If `derivedField` = 'billGroup' is found (path: `referenceData.derivedFields.derivedField`):\n")
                .append("           - Check the `coTypes` list for 'DN' (path: `referenceData.derivedFields.coTypes`).\n")
                .append("           - If 'DN' is found, set `DN_BillGroupReferenceID` to blank.\n")
                .append("           - If 'DN' is not found, randomize a value from `billGroups` in `planData` where `coverageOptionType` = 'DN' (path: `referenceData.planData.billGroups`).\n")
                .append("       12.2.4 If `derivedField` = 'billGroup' is not found:\n")
                .append("           - Randomize a value from `billGroups` in `planData` where `coverageOptionType` = 'DN' (path: `referenceData.planData.billGroups`).\n")
                .append("       12.2.5 Ensure all members of the same family have the same `DN_BillGroupReferenceID`.\n")
                .append("       12.2.6 Spouse and child cannot have any value that the subscriber doesn't.\n")
                .append("       12.2.7 `DN_BillGroupReferenceID` is mandatory for all individuals if there is no derived field.\n\n")
                .append("   12.3 **VS_BillGroupReferenceID:**\n")
                .append("       12.3.1 Parse the `referenceData` JSON.\n")
                .append("       12.3.2 Check for the `derivedFields` key (path: `referenceData.derivedFields`).\n")
                .append("       12.3.3 If `derivedField` = 'billGroup' is found (path: `referenceData.derivedFields.derivedField`):\n")
                .append("           - Check the `coTypes` list for 'VS' (path: `referenceData.derivedFields.coTypes`).\n")
                .append("           - If 'VS' is found, set `VS_BillGroupReferenceID` to blank.\n")
                .append("           - If 'VS' is not found, randomize a value from `billGroups` in `planData` where `coverageOptionType` = 'VS' (path: `referenceData.planData.billGroups`).\n")
                .append("       12.3.4 If `derivedField` = 'billGroup' is not found:\n")
                .append("           - Randomize a value from `billGroups` in `planData` where `coverageOptionType` = 'VS' (path: `referenceData.planData.billGroups`).\n")
                .append("       12.3.5 Ensure all members of the same family have the same `VS_BillGroupReferenceID`.\n")
                .append("       12.3.6 Spouse and child cannot have any value that the subscriber doesn't.\n")
                .append("       12.3.7 `VS_BillGroupReferenceID` is mandatory for all individuals if there is no derived field.\n\n")
                .append("   12.4 **Validation Rules:**\n")
                .append("       - Ensure all members of the same family share the same `BillGroupReferenceID`.\n")
                .append("       - Spouse/child cannot have values that the subscriber lacks.\n")
                .append("       - Ensure correct mapping: `MD` data should only be used for `MD_BillGroupReferenceID`, `DN` for `DN_BillGroupReferenceID`, and `VS` for `VS_BillGroupReferenceID`.\n")
                .append("       - If no matching object is found for a coverage type, set the value to blank.\n\n")





    public String getReferenceData() {
        StringBuilder referenceData = new StringBuilder();
        referenceData.append("'''     \"   \\\"derivedFields\\\":[\\n\" +\n" +
                                "                        \"      {\\n\" +\n" +
                                "                        \"         \\\"derivedField\\\":\\\"coveragePopulation\\\",\\n\" +\n" +
                                "                        \"         \\\"derivedEffectiveDate\\\":\\\"\\\",\\n\" +\n" +
                                "                        \"         \\\"derivedExpirationDate\\\":\\\"\\\",\\n\" +\n" +
                                "                        \"         \\\"coTypes\\\":['MD','DN','VS']\\n\" +\n" +
                                "                        \"      },\\n\" +\n" +
                                "                        \"      {\\n\" +\n" +
                                "                        \"         \\\"derivedField\\\":\\\"billGroup\\\",\\n\" +\n" +
                                "                        \"         \\\"derivedEffectiveDate\\\":\\\"\\\",\\n\" +\n" +
                                "                        \"         \\\"derivedExpirationDate\\\":\\\"\\\",\\n\" +\n" +
                                "                        \"         \\\"coTypes\\\":['MD','DN','VS']\\n\" +\n" +
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

