11. **Coverage Population ID Assignment:**  
    - Parse `referenceData` and locate the `derivedFields` array.  
    - Search for an object where `derivedField` = "coveragePopulation".  
    - If found, check `coTypes` inside that object:  
        - If `MD` is present in `coTypes`, set `MD_CoveragePopulationID` to blank.  
        - If `DN` is present in `coTypes`, set `DN_CoveragePopulationID` to blank.  
        - If `VS` is present in `coTypes`, set `VS_CoveragePopulationID` to blank.  
    - If `derivedField` = "coveragePopulation" is not found OR `coTypes` does not contain the relevant type:  
        - Assign a random value from `planData.coveragePopulations` where `coverageOptionType` matches the respective category (`MD`, `DN`, `VS`).  
    - Ensure all members of the same family share the same `CoveragePopulationID`.  
    - Spouse and child cannot have any value that the subscriber does not.  
    - `CoveragePopulationID` is mandatory for all individuals if no derived field is found.
   

12. **Bill Group Reference Assignment:**  
    - Parse `referenceData` and locate the `derivedFields` array.  
    - Search for an object where `derivedField` = "billGroup".  
    - If found, check `coTypes` inside that object:  
        - If `MD` is present in `coTypes`, set `MD_BillGroupReferenceID` to blank.  
        - If `DN` is present in `coTypes`, set `DN_BillGroupReferenceID` to blank.  
        - If `VS` is present in `coTypes`, set `VS_BillGroupReferenceID` to blank.  
    - If `derivedField` = "billGroup" is not found OR `coTypes` does not contain the relevant type:  
        - Assign a random value from `planData.billGroups` where `coverageOptionType` matches the respective category (`MD`, `DN`, `VS`).  
    - Ensure all members of the same family share the same `BillGroupReferenceID`.  
    - Spouse and child cannot have any value that the subscriber does not.  
    - `BillGroupReferenceID` is mandatory for all individuals if no derived field is found.  
