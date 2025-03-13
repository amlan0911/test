.append("10. **Coverage Data Assignment:**\n")
                .append("   10.1 **MD_CoverageOptionID**: Extract `bundleOptionID` where `coverageOptionType='MD'` from `referenceData.planData`. If `bundleOptionID` where `coverageOptionType='MD'` is not found, then explicitly set `MD_CoverageOptionID = \"NULL\"` (do not assign any value).\n")
                .append("   10.2 **DN_CoverageOptionID**: Extract `bundleOptionID` where `coverageOptionType='DN'` from `referenceData.planData`. If `bundleOptionID` where `coverageOptionType='DN'` is not found, then explicitly set `DN_CoverageOptionID = \"NULL\"` (do not assign any value).\n")
                .append("   10.3 **VS_CoverageOptionID**: Extract `bundleOptionID` where `coverageOptionType='VS'` from `referenceData.planData`. If `bundleOptionID` where `coverageOptionType='VS'` is not found, then explicitly set `VS_CoverageOptionID = \"NULL\"` (do not assign any value).\n\n")
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

