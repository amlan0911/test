.append("10. Coverage Data Assignment:\n")
.append(" 10.1 Read `referenceData.planData`, an array of JSON objects where each object has a `coverageOptionType` key.\n")
.append(" 10.2 Extract `bundleOptionID` where `coverageOptionType = MD` from `planData`. If not found, set `MD_CoverageOptionID = NULL`.\n")
.append(" 10.3 Extract `bundleOptionID` where `coverageOptionType = DN` from `planData`. If not found, set `DN_CoverageOptionID = NULL`.\n")
.append(" 10.4 Extract `bundleOptionID` where `coverageOptionType = VS` from `planData`. If not found, set `VS_CoverageOptionID = NULL`.\n\n")

.append("11. Coverage Population ID Assignment:\n")
.append(" 11.1 Read `referenceData.derivedFields`, an array of JSON objects where each object has a `derivedField` key.\n")
.append(" 11.2 Find an object where `derivedField = coveragePopulation`.\n")
.append(" 11.3 If found, extract the `coTypes` array from that object.\n")
.append(" 11.4 If `coTypes` contains `MD`, set `MD_CoveragePopulationID = NULL`.\n")
.append(" 11.5 If `coTypes` contains `DN`, set `DN_CoveragePopulationID = NULL`.\n")
.append(" 11.6 If `coTypes` contains `VS`, set `VS_CoveragePopulationID = NULL`.\n")
.append(" 11.7 If `coveragePopulation` is missing OR `coTypes` does not contain `MD`, `DN`, or `VS`:\n")
.append("      - Assign a random value from `planData.coveragePopulations` where `coverageOptionType` matches.\n")
.append(" 11.8 Ensure all members of the same family share the same `CoveragePopulationID`.\n")
.append(" 11.9 Spouse and child cannot have any value that the subscriber does not.\n")
.append(" 11.10 If `MD_CoveragePopulationID`, `DN_CoveragePopulationID`, or `VS_CoveragePopulationID` is already `NULL`, do not assign any value later.\n\n")

.append("12. Bill Group Reference Assignment:\n")
.append(" 12.1 Read `referenceData.derivedFields`, an array of JSON objects where each object has a `derivedField` key.\n")
.append(" 12.2 Find an object where `derivedField = billGroup`.\n")
.append(" 12.3 If found, extract the `coTypes` array from that object.\n")
.append(" 12.4 If `coTypes` contains `MD`, set `MD_BillGroupReferenceID = NULL`.\n")
.append(" 12.5 If `coTypes` contains `DN`, set `DN_BillGroupReferenceID = NULL`.\n")
.append(" 12.6 If `coTypes` contains `VS`, set `VS_BillGroupReferenceID = NULL`.\n")
.append(" 12.7 If `billGroup` is missing OR `coTypes` does not contain `MD`, `DN`, or `VS`:\n")
.append("      - Assign a random value from `planData.billGroups` where `coverageOptionType` matches.\n")
.append(" 12.8 Ensure all members of the same family share the same `BillGroupReferenceID`.\n")
.append(" 12.9 Spouse and child cannot have any value that the subscriber does not.\n")
.append(" 12.10 If `MD_BillGroupReferenceID`, `DN_BillGroupReferenceID`, or `VS_BillGroupReferenceID` is already `NULL`, do not assign any value later.\n\n");
