    public static final String GENERIC_PROMPT_CSV = "You are DataGen, an expert AI tool specializing in generating synthetic data with strict adherence to rules. Your primary task is to generate valid CSV data based on provided headers and instructions. Follow these steps to ensure accuracy and compliance: \n" +
            "1. Generate Rows: Create rows based on the received CSV header..\n" +
            "2. Populate Values: Fill the rows with values using ',' as the delimiter, following the provided instructions.\n" +
            "3. Validate Data: Ensure the generated data complies with the instructions.\n" +
            "4. Correct Discrepancies: Fix any issues found during validation.\n" +
            "5. Output Valid Data: Return only the valid CSV including only validated data rows.\n\n" +
            "Your response should strictly include a valid CSV format with randomized data and no extraneous text.\n";



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
                .append("MD_BillGroupReferenceID") .append("DN_BillGroupReferenceID") .append("VS_BillGroupReferenceID");
        return csv.toString();
    }

public String getInstructions() {
    StringBuilder instructionsCsv = new StringBuilder();
    instructionsCsv.append("1. Fetch Members:\n")
            .append("   1.1 Fetch the requested number of members from the user prompt.\n")
            .append("   1.2 Each member denotes one family.\n")
            .append("   1.3 Each family can have 1 to 3 individuals.\n")
            .append("2. Individual Representation:\n")
            .append("   2.1 Each row will represent one individual, who can be part of a family.\n")
            .append("   2.2 Assign the `memberGroupID` from the user prompt to each individual.\n")
            .append("3. Generate Unique IDs:\n")
            .append("   3.1 Generate a unique 9-digit `affiliationExternalID` for each family requested in the user prompt.\n")
            .append("   3.2 Ensure the number of unique `affiliationExternalID`s matches the number of requested members before proceeding.\n")
            .append("4. Family Composition:\n")
            .append("   4.1 Each family must have one subscriber.\n")
            .append("   4.2 Optionally, a family can have one spouse and one child.\n")
            .append("5. Assign Relationship Codes:\n")
            .append("   5.1 Assign `relationshipCode` values as follows:\n")
            .append("       - 18 for the subscriber\n")
            .append("       - 01 for the spouse\n")
            .append("       - 19 for the child\n")
            .append("6. Set Employment Details:\n")
            .append("   6.1 Set `employBeginDate` as 01/01/2025 only for subscribers (`relationshipCode`=18) and leave it blank for others.\n")
            .append("   6.2 Set `employStatusCode` as 'A' only for subscribers.\n")
            .append("7. Validation and Correction:\n")
            .append("   7.1 Validate that the final CSV response has the exact number of families/externalAffiliationIDs as requested by the user.\n")
            .append("   7.2 If the validation fails, correct the data to ensure accuracy.\n")
            .append("8. Assign Contact details:\n")
            .append("   8.1 Assign `firstName` and `lastName`: Use any valid first name and last name.\n")
            .append("   8.2 Generate `birthDate`: Ensure the `birthDate` is not greater than 150 years from today.\n")
            .append("   8.3 Assign `gender`: Randomize among 'M', 'F', 'U'.\n")
            .append("   8.4 Set `addressType`: Default to 'HOM'.\n")
            .append("   8.5 Assign `address1`: Use any valid USA address.\n")
            .append("   8.6 Randomize a valid combination of `city`, `state`, and `postalCode` from USA.\n")
            .append("   8.7 Set `country`: Default to 'US'.\n")
            .append("   8.8 Set `communicationType`: Default to 'EML'.\n")
            .append("   8.9 Generate `communicationText`: Randomize email id based on member name, format firstname_lastname@test.com.\n")
            .append("   8.10 Set `externalIDType`: Default to '0F'.\n")
            .append("9. Benefit Details:\n")
            .append("   9.1 Set `benefitEffectiveDate`: Use the value of the `benefitEffectiveDate` key from the `referenceData`.\n")
            .append("   9.2 Set `qualifyingEvent`: Default to '28'.\n")
            .append("   9.3 Set `qualifyingEventDate`: Use the value of the `benefitEffectiveDate` key from the `referenceData`.\n")
            .append("   9.4 Set `MD_CoverageOptionID`:\n")
            .append("       9.4.1 Parse the `referenceData` JSON.\n")
            .append("       9.4.2 Navigate to `planData` (path: `referenceData.planData`).\n")
            .append("       9.4.3 Find an object with `coverageOptionType` = 'MD' (path: `referenceData.planData.coverageOptionType`).\n")
            .append("       9.4.4 If found, pull the `bundleOptionID` (path: `referenceData.planData.bundleOptionID`).\n")
            .append("       9.4.5 Set `MD_CoverageOptionID` to the pulled `bundleOptionID`.\n")
            .append("       9.4.6 If not found, set `MD_CoverageOptionID` to blank.\n")
            .append("   9.5 Set `DN_CoverageOptionID`:\n")
            .append("       9.5.1 Parse the `referenceData` JSON.\n")
            .append("       9.5.2 Navigate to `planData` (path: `referenceData.planData`).\n")
            .append("       9.5.3 Find an object with `coverageOptionType` = 'DN' (path: `referenceData.planData.coverageOptionType`).\n")
            .append("       9.5.4 If found, pull the `bundleOptionID` (path: `referenceData.planData.bundleOptionID`).\n")
            .append("       9.5.5 Set `DN_CoverageOptionID` to the pulled `bundleOptionID`.\n")
            .append("       9.5.6 If not found, set `DN_CoverageOptionID` to blank.\n")
            .append("   9.6 Set `VS_CoverageOptionID`:\n")
            .append("       9.6.1 Parse the `referenceData` JSON.\n")
            .append("       9.6.2 Navigate to `planData` (path: `referenceData.planData`).\n")
            .append("       9.6.3 Find an object with `coverageOptionType` = 'VS' (path: `referenceData.planData.coverageOptionType`).\n")
            .append("       9.6.4 If found, pull the `bundleOptionID` (path: `referenceData.planData.bundleOptionID`).\n")
            .append("       9.6.5 Set `VS_CoverageOptionID` to the pulled `bundleOptionID`.\n")
            .append("       9.6.6 If not found, set `VS_CoverageOptionID` to blank.\n")
            .append("   9.7 Set `MD_coveragePopulationID`:\n")
            .append("       9.7.1 Parse the `referenceData` JSON.\n")
            .append("       9.7.2 Check for the `derivedFields` key (path: `referenceData.derivedFields`).\n")
            .append("       9.7.3 If `derivedField` = 'coveragePopulation' is found (path: `referenceData.derivedFields.derivedField`):\n")
            .append("           - Check the `coTypes` list for 'MD' (path: `referenceData.derivedFields.coTypes`).\n")
            .append("           - If 'MD' is found, set `MD_coveragePopulationID` to blank.\n")
            .append("           - If 'MD' is not found, randomize a value from `coveragePopulations` in `planData` where `coverageOptionType` = 'MD' (path: `referenceData.planData.coveragePopulations`).\n")
            .append("       9.7.4 If `derivedField` = 'coveragePopulation' is not found:\n")
            .append("           - Randomize a value from `coveragePopulations` in `planData` where `coverageOptionType` = 'MD' (path: `referenceData.planData.coveragePopulations`).\n")
            .append("       9.7.5 Ensure all members of the same family have the same `MD_coveragePopulationID`.\n")
            .append("       9.7.6 Spouse and child cannot have any value that the subscriber doesn't.\n")
            .append("       9.7.7 `MD_coveragePopulationID` is mandatory for all individuals if there is no derived field.\n")
            .append("   9.8 Set `DN_coveragePopulationID`:\n")
            .append("       9.8.1 Parse the `referenceData` JSON.\n")
            .append("       9.8.2 Check for the `derivedFields` key (path: `referenceData.derivedFields`).\n")
            .append("       9.8.3 If `derivedField` = 'coveragePopulation' is found (path: `referenceData.derivedFields.derivedField`):\n")
            .append("           - Check the `coTypes` list for 'DN' (path: `referenceData.derivedFields.coTypes`).\n")
            .append("           - If 'DN' is found, set `DN_coveragePopulationID` to blank.\n")
            .append("           - If 'DN' is not found, randomize a value from `coveragePopulations` in `planData` where `coverageOptionType` = 'DN' (path: `referenceData.planData.coveragePopulations`).\n")
            .append("       9.8.4 If `derivedField` = 'coveragePopulation' is not found:\n")
            .append("           - Randomize a value from `coveragePopulations` in `planData` where `coverageOptionType` = 'DN' (path: `referenceData.planData.coveragePopulations`).\n")
            .append("       9.8.5 Ensure all members of the same family have the same `DN_coveragePopulationID`.\n")
            .append("       9.8.6 Spouse and child cannot have any value that the subscriber doesn't.\n")
            .append("       9.8.7 `DN_coveragePopulationID` is mandatory for all individuals if there is no derived field.\n")
            .append("   9.9 Set `VS_coveragePopulationID`:\n")
            .append("       9.9.1 Parse the `referenceData` JSON.\n")
            .append("       9.9.2 Check for the `derivedFields` key (path: `referenceData.derivedFields`).\n")
            .append("       9.9.3 If `derivedField` = 'coveragePopulation' is found (path: `referenceData.derivedFields.derivedField`):\n")
            .append("           - Check the `coTypes` list for 'VS' (path: `referenceData.derivedFields.coTypes`).\n")
            .append("           - If 'VS' is found, set `VS_coveragePopulationID` to blank.\n")
            .append("           - If 'VS' is not found, randomize a value from `coveragePopulations` in `planData` where `coverageOptionType` = 'VS' (path: `referenceData.planData.coveragePopulations`).\n")
            .append("       9.9.4 If `derivedField` = 'coveragePopulation' is not found:\n")
            .append("           - Randomize a value from `coveragePopulations` in `planData` where `coverageOptionType` = 'VS' (path: `referenceData.planData.coveragePopulations`).\n")
            .append("       9.9.5 Ensure all members of the same family have the same `VS_coveragePopulationID`.\n")
            .append("       9.9.6 Spouse and child cannot have any value that the subscriber doesn't.\n")
            .append("       9.9.7 `VS_coveragePopulationID` is mandatory for all individuals if there is no derived field.\n")
            .append("   9.10 Set `MD_BillGroupReferenceID`:\n")
            .append("       9.10.1 Parse the `referenceData` JSON.\n")
            .append("       9.10.2 Check for the `derivedFields` key (path: `referenceData.derivedFields`).\n")
            .append("       9.10.3 If `derivedField` = 'billGroup' is found (path: `referenceData.derivedFields.derivedField`):\n")
            .append("           - Check the `coTypes` list for 'MD' (path: `referenceData.derivedFields.coTypes`).\n")
            .append("           - If 'MD' is found, set `MD_BillGroupReferenceID` to blank.\n")
            .append("           - If 'MD' is not found, randomize a value from `billGroups` in `planData` where `coverageOptionType` = 'MD' (path: `referenceData.planData.billGroups`).\n")
            .append("       9.10.4 If `derivedField` = 'billGroup' is not found:\n")
            .append("           - Randomize a value from `billGroups` in `planData` where `coverageOptionType` = 'MD' (path: `referenceData.planData.billGroups`).\n")
            .append("       9.10.5 Ensure all members of the same family have the same `MD_BillGroupReferenceID`.\n")
            .append("       9.10.6 Spouse and child cannot have any value that the subscriber doesn't.\n")
            .append("       9.10.7 `MD_BillGroupReferenceID` is mandatory for all individuals if there is no derived field.\n")
            .append("   9.11 Set `DN_BillGroupReferenceID`:\n")
            .append("       9.11.1 Parse the `referenceData` JSON.\n")
            .append("       9.11.2 Check for the `derivedFields` key (path: `referenceData.derivedFields`).\n")
            .append("       9.11.3 If `derivedField` = 'billGroup' is found (path: `referenceData.derivedFields.derivedField`):\n")
            .append("           - Check the `coTypes` list for 'DN' (path: `referenceData.derivedFields.coTypes`).\n")
            .append("           - If 'DN' is found, set `DN_BillGroupReferenceID` to blank.\n")
            .append("           - If 'DN' is not found, randomize a value from `billGroups` in `planData` where `coverageOptionType` = 'DN' (path: `referenceData.planData.billGroups`).\n")
            .append("       9.11.4 If `derivedField` = 'billGroup' is not found:\n")
            .append("           - Randomize a value from `billGroups` in `planData` where `coverageOptionType` = 'DN' (path: `referenceData.planData.billGroups`).\n")
            .append("       9.11.5 Ensure all members of the same family have the same `DN_BillGroupReferenceID`.\n")
            .append("       9.11.6 Spouse and child cannot have any value that the subscriber doesn't.\n")
            .append("       9.11.7 `DN_BillGroupReferenceID` is mandatory for all individuals if there is no derived field.\n")
            .append("   9.12 Set `VS_BillGroupReferenceID`:\n")
            .append("       9.12.1 Parse the `referenceData` JSON.\n")
            .append("       9.12.2 Check for the `derivedFields` key (path: `referenceData.derivedFields`).\n")
            .append("       9.12.3 If `derivedField` = 'billGroup' is found (path: `referenceData.derivedFields.derivedField`):\n")
            .append("           - Check the `coTypes` list for 'VS' (path: `referenceData.derivedFields.coTypes`).\n")
            .append("           - If 'VS' is found, set `VS_BillGroupReferenceID` to blank.\n")
            .append("           - If 'VS' is not found, randomize a value from `billGroups` in `planData` where `coverageOptionType` = 'VS' (path: `referenceData.planData.billGroups`).\n")
            .append("       9.12.4 If `derivedField` = 'billGroup' is not found:\n")
            .append("           - Randomize a value from `billGroups` in `planData` where `coverageOptionType` = 'VS' (path: `referenceData.planData.billGroups`).\n")
            .append("       9.12.5 Ensure all members of the same family have the same `VS_BillGroupReferenceID`.\n")
            .append("       9.12.6 Spouse and child cannot have any value that the subscriber doesn't.\n")
            .append("       9.12.7 `VS_BillGroupReferenceID` is mandatory for all individuals if there is no derived field.\n")
            .append("User Query Example:\n")
            .append("   - \"Enroll 10 members\" should result in data for 10 families.\n");

    return instructionsCsv.toString();
}


    public StringBuilder getValidationInstructions() {
        StringBuilder validationInstructions = new StringBuilder();
        validationInstructions.append("The number of affiliationExternalID created in the previous CSV response needs to match the initial number of members requested in the user prompt. " +
                "If not correct, then add or delete rows as required with right data.");

        return validationInstructions;
    }


    public String getReferenceData() {
        StringBuilder referenceData = new StringBuilder();
        referenceData.append("'''{\n" +
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
                        "   },\n" +
                        "   \"derivedFields\":[\n" +
                        "      {\n" +
                        "         \"derivedField\":\"coveragePopulation\",\n" +
                        "         \"derivedEffectiveDate\":\"\",\n" +
                        "         \"derivedExpirationDate\":\"\",\n" +
                        "         \"coTypes\":['MD','DN','VS']\n" +
                        "      },\n" +
                        "      {\n" +
                        "         \"derivedField\":\"billGroup\",\n" +
                        "         \"derivedEffectiveDate\":\"\",\n" +
                        "         \"derivedExpirationDate\":\"\",\n" +
                        "         \"coTypes\":['MD','DN','VS']\n" +
                        "         ]\n" +
                        "      }\n" +
                        "   ]\n" +
                        "} ")
                .append(" '''")
                .append("\n");
        return referenceData.toString();
    }


