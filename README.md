<!DOCTYPE html>
<html>
<head>
  <title>Water Treatment Shuffled Quiz</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 20px;
      background-color: black;
      color: white;
    }

    .question {
      margin-bottom: 30px;
      padding: 15px;
      border: 1px solid #ccc;
      border-radius: 6px;
      background-color: #222;
      color: white;
    }

    .question h3 {
      margin: 0 0 10px;
      color: white;
    }

    .feedback {
      font-weight: bold;
    }

    .correct {
      color: lightblue;
    }

    .incorrect {
      color: #C43802;
    }

    .action-row {
      display: flex;
      align-items: center;
      gap: 15px;
      margin-top: 10px;
    }

    button {
      padding: 6px 12px;
      font-size: 14px;
      cursor: pointer;
    }

    #shuffle-btn {
      margin-top: 30px;
      padding: 10px 20px;
      font-size: 16px;
      color: blue;
      background-color: #111;
      border: 1px solid #444;
      border-radius: 6px;
    }
  </style>
</head>
<body>
  <h2 style="color: yellow;">Water Treatment Quiz</h2>
  <div id="quiz-container"></div>
  <button id="shuffle-btn" onclick="shuffleQuestions()">🔄 Shuffle Questions</button>

  <script>
    const questions = [


        {question: "Detention time in flocculation basins are usually designed to provide for?",
            options: ["1-5 seconds", "15-45 seconds", "15-45 mins", "1-5 mins"],
                answer: 2 },
        {question: "What is the sticky mat and fine sand of suspended matter that forms on the surface of a sand filter?",
            options: ["Schmutzdecke", "Chlorine Residual", "THM's", "Pre-Filter Beads"],
                answer: 0 },
        {question: "What is the MCLG for chloride?",
            options: ["250 mg/L", "142 mg/L", "45 ppm", "0 mg/L"],
                answer: 0 },
        {question: "What works best to disinfect cryptosporidium?",
            options: ["Filtration", "Cl2", "CL2 + Ammonia", "Ozone"],
                answer: 3 },
        {question: "Under the Surface Water Treatment Rule a multiple barrier treatment consists of",
            options: ["Removal by filtration and inactivation by disinfection", "Coagulation, Flocculation, Sedimentation", "CT Value, Residual, Filter", "Bar Screens, Filters, Ozone"],
                answer: 0 },
        {question: "As CaCO3 how much alkalinity will dry-basis alum consume?",
            options: ["0.5 mg/L", "0.8 mg/L", "1.1 mg/L", "1.4 mg/L"],
                answer: 0 },
        {question: "What is an employee's average airborne exposure in any 8 hour shift in a 40 hour work week that should not be exceeded called?",
            options: ["Recommended Exposure Limits (REL)", "Threshold Limit Value (TLV)", "Time Weighted Average (TWA)", "Short Term Exposure Limit (STEL)"],
                answer: 2 },
        {question: "Why are polyphosphates used in drinking water?",
            options: ["To Prevent the Formation of Nitrates", "To Keep Chlorine and Ammonia Combined", "To Keep Iron and Manganese in Sequestration", "To Prevent Corrosion of PVC and AC Pipes"],
                answer: 2 },
        {question: "Fluoride concentration above what mg/L will likely cause teeth to become pitted?",
            options: [".01 mg/L", "2 mg/L", "4 mg/L", "5 mg/L"],
                answer: 2 },
        {question: "What is the process that is used to dewater sludge?",
            options: ["Thickener", "Wash Water Basin", "Sand Bed", "Relaim Basin"],
                answer: 2 },
        {question: "The Zeta Protentional measures the number of excess what found on the surface of all particular matter?",
            options: ["Electrons", "Organics", "Inorganics", "Bacteria"],
                answer: 0 },
        {question: "What will increase alkalinity, pH, and hardness?",
            options: ["Sodium Zinc Phosphate", "Zinc", "Lime", "Sodium Hydroxide"],
                answer: 2 },
        {question: "What do long filter runs tend to cause?",
            options: ["Slime Growths", "Shorter Run Times", "The clogging of chlorometers", "Loss of Operator Interest"],
                answer: 0 },
        {question: "What is the depression around the well of the water surface caused by pumping water from a well?",
            options: ["Aquifer", "Cone of Depression", "Crater", "Vendor"],
                answer: 1 },
        {question: "Floc is produced when there is a chemical reaction between the coagulant and alkalinity. If the alkalinity of raw water is too low the floc formation will be poor. Some form of alkalinity must be added if the amount that is naturally found in the water source is less than?",
            options: ["80 mg/L", "100 mg/L", "150 mg/L", "200 mg/L"],
                answer: 0 },
        {question: "The most accurate chlorine residual measurement would be taken with?",
            options: ["DPD", "pH Meter", "Jar Test", "Amperometric Titration"],
                answer: 3 },
        {question: "What is the most effective method for removing tastes and odors?",
            options: ["Granular Activated Carbon", "Coagulation, Sedimentation, and Filtration", "Lime Softening", "Anion Exchange"],
                answer: 0 },
        {question: "Which is the method for testing for total coliform bacteria?",
            options: ["ABC Method", "B&G Method", "MTF Method", "All of the above"],
                answer: 2 },
        {question: "What disinfectant is commonly used and free of Cl2 to avoid THMs?",
            options: ["Hydrogen Peroxide", "Poly-Phosphate", "CaCO2", "Ozone Gas"],
                answer: 3 },
        {question: "It is important not to rinse out the sample bottes used for collecting samples for bacteriological examination because?",
            options: ["The acid in the sample to preserve it will get rinsed out", "The water may splash on the sample taker", "The sodium thiosulfate crystals inside the bottle neutralize the chlorine present in the sample", "The sample must be a first draw sample from the tap"],
                answer: 2 },
        {question: "An increase in filter media head loss could be an indicator of?",
            options: ["Carryover from the Sedimentation Basin", "Filter is Ripening", "Filter run is short", "Flux Capacitor is clogged"],
                answer: 0 },
        {question: "When disinfecting a well with free chlorine, what is the required exposure time and what must the concentration be?",
            options: ["1 to 2 mins with 50 mg/L", "1 to 2 hrs with 100 mg/L", "6 to 8 hrs with 25 mg/L", "12 to 24hrs with 50 mg/L"],
                answer: 3 },
        {question: "The IDLH (immediately dangerous to life and health) value for chlorine is?",
            options: ["5 ppm", "10 ppm", "15 ppm", "25 ppm"],
                answer: 1 },
        {question: "What could happen if the sludge in a sedimentation basin becomes too thick?",
            options: ["Solids can become resuspended or taste and odors can develop", "The sludge will compact at the bottom of the basin", "Gases from decomposition will rise through the settled sludge", "Abundant THMs and HAAA5s acids will form"],
                answer: 0 },
        {question: "What does a high pH favor the formation of?",
            options: ["Both Haloacetic Acids and Total Trihalomethanes", "Neither Haloacetic Acids and Total Trihalomethanes", "Total Trihalomethanes", "Haloacetic Acids"],
                answer: 2 },
        {question: "What agency should be called for actual hands on assistance if a substantial chlorine leak incident occurs?",
            options: ["Chemical Transportation Emergency Center", "Chlorine Institute", "Occupational Safety and Health Administration", "Transportation Emergency Institute"],
                answer: 0 },
        {question: "The proper emergency kit for a chlorine tanker is?",
            options: ["Kit A", "Kit B", "Kit C", "Kit from Knight Rider"],
                answer: 2 },
        {question: "Which is the strongest disinfectant?",
            options: ["Chloramine", "Hypochlorous Acid", "Nitrogen Manganese", "Carbonic Kryptonium"],
                answer: 1 },
        {question: "What term describes the gathering of colloids into larger particles?",
            options: ["Agglomeration", "Flocculation", "Combining", "The Gathering"],
                answer: 0 },
        {question: "What is the total concentration of dissolved solids in the wastewater from the regeneration of ion exchange units?",
            options: ["5,00 to 10,000 mg/L", "15,00 to 25,000 mg/L", "26,00 to 27,000 mg/L", "35,00 to 45,000 mg/L"],
                answer: 3 },
        {question: "Post sedimentation process, the turbidity of settled water before it is applied to the filters should be kept below?",
            options: ["1 - 2 ntu", "3-5 ntu", "7-9 ntu", "13+ ntu"],
                answer: 0 },
        {question: "What chemical can be created by certain bacterial organisms and accelerate the corrosion process?",
            options: ["CaCO3", "N2", "CO2", "MgCO3"],
                answer: 2 },
        {question: "What is the specific gravity standard for gases?",
            options: ["Air", "Water Vapor at 100 Degrees Celsius", "Nitrogen", "Kryptonite"],
                answer: 0 },
        {question: "What is the only MCL that varies with the temperature?",
            options: ["Fluoride", "Arsenic", "Chloramines", "Sodium Hydroxide"],
                answer: 0 },
        {question: "What is the cause of temporary hardness?",
            options: ["Magnesium Chloride", "Calcium Bicarbonate", "Calcium Nitrate", "Magnesium Sulfate"],
                answer: 1 },
        {question: "One of the steps taken to determine the threshold odor number is?",
            options: ["Counting the number of organisms that cause odor", "Diluting the sample with distilled water", "Jar Test with Smell Test", "bac-T Test"],
                answer: 1 },
        {question: "What is recarbonation?",
            options: ["Adding CO2 to the water", "Letting water shake in a take or settling basin", "Adding more Hydrogen to the water", "Adding Soda Ash to the water"],
                answer: 0 },
        {question: "If dry alum and quicklime are mixed together, what will happen?",
            options: ["Dust will be Created", "Highly Explosive Hydrogen Gas will be Released", "A Gel will Form", "None of the above"],
                answer: 1 },
        {question: "What is the motion called for the particles in water that are in constant motion and work in conjunction with the destabilization process to create floc?",
            options: ["van der Waal's force", "Zeta Potential", "Galvanic Condition", "Brownian Movement"],
                answer: 3 },
        {question: "In pounds, how much ammonia is contained in a 1 ton cylinder that is full?",
            options: ["800", "1000", "1500", "2000"],
                answer: 0 },
        {question: "Settled backwash water that is recovered and re-used from a conventional surface water filtration plant should be returned to the beginning of the treatment train.",
            options: ["TRUE", "FALSE", "na", "na"],
                answer: 0 },
        {question: "What is the main function of a flocculation basin?",
            options: ["Settle suspended solids", "Allow for contact time", "Allow suspended particles to aggregate", "Allow Cl2 to react"],
                answer: 2 },
        {question: "What was created to have uniform standards in Water Treatment?",
            options: ["The Safe Drinking Water Act", "USEPA", "Title 22", "Universal Plumbing Code -UPC"],
                answer: 0 },
        {question: "What two principles cause water hardness?",
            options: ["Iron and Manganese", "Aluminum and Iron", "Aluminum and Calcium", "Calcium and Magnesium"],
                answer: 3 },
        {question: "Which forces will pull particles together once they have been destabilized in the coagulation-flocculation process?",
            options: ["Van der Waals Forces", "Gravitational Forces", "G-Forces", "Pressure Force"],
                answer: 0 },
        {question: "What is the usual range of percent sludge solids, if the sludge is allowed to accumulate and compact at the bottom of a sedimentation basin?",
            options: ["2-4%", "6-8%", "12-24%", "42-57%"],
                answer: 0 },
        {question: "What is the typical strength of calcium hypochlorite?",
            options: ["5-15%", "65-70%", "20-25%", "75-99%"],
                answer: 0 },
        {question: "Fine solids that remain suspended in water and will not settle on their own are known as?",
            options: ["THM's", "HAA5s", "Chlorine Residuals", "Colloids"],
                answer: 0 },
        {question: "What is the most favorable raw water condition for good flocculation?",
            options: ["High pH and High Alkalinity", "Low pH and High Alkalinity", "Low pH and Low Alkalinity", "High pH and Low Alkalinity"],
                answer: 1 },
        {question: "What angle should the parallel inclined plates be installed when using the shallow depth sedimentation method?",
            options: ["25 degrees", "45 degrees", "50 degrees", "90 degrees"],
                answer: 1 },
        {question: "If there is debris found in the filter bed after backwashing a filter this can indicate?",
            options: ["The backwash rate is too low", "Too many THMs", "Low Ammonia", "The backwash rate is too high"],
                answer: 0 },
        {question: "A test(s) used to monitor the disinfection processes would be?",
            options: ["Chlorine Residual", "Bacteriological Testing", "HPC Counts", "All of the Above"],
                answer: 3 },
        {question: "Organic chemistry is concerned with compounds containing what element?",
            options: ["Iron", "Manganese", "Carbon", "Sulfur"],
                answer: 2 },
        {question: "If sodium hypochlorite comes into contact with the skin or eyes, the area should be flushed with water for at least 15 minutes.",
            options: ["1 min", "15 mins", "5 mins", "3 mins"],
                answer: 1 },
        {question: "Chlorine gas ton cylinders include two feed line connections. One is an upper and one is a lower that is designed to?",
            options: ["Both Feed Gas", "Neither feed gas, they are for pressure release", "Both lines are used to keep tank from freezing", "Only the top feed line feeds the chlorine gas"],
                answer: 3 },
        {question: "What is usually used to disinfect the gravel packing of a ground water well?",
            options: ["Chloramines", "Powder of Calcium Hypochlorite tablet", "Sodium Hypochlorite", "Chlorine Dioxide"],
                answer: 1 },
        {question: "What gas can cause lung and skin irritation?",
            options: ["Oxygen", "Chlorine", "Diesel", "Magnesium"],
                answer: 1 },
        {question: "The Colilert test (ONPG-MUG) shows the presence of total coliforms is shown by?",
            options: ["A Red/Pink Water Color", "A Yellow Water Color", "A Green Water Color", "A Blue Water Color"],
                answer: 1 },
        {question: "Never apply water to a gaseous chlorine leak because the water will cause more issues.",
            options: ["TRUE", "FALSE", "na", "na"],
                answer: 0 },
        {question: "In alum sludge, what is typically the percentage of solid material?",
            options: ["0.1 to 2.0%", "2.0 to 5.0%", "7 to 10%", "25 to 50%"],
                answer: 0 },
        {question: "The hour during the day when the largest volume of water is being pumped is known as peak hourly flow?",
            options: ["TRUE", "FALSE", "na", "na"],
                answer: 0 },
        {question: "Plant growth in a reservoir will usually be found at a depth of?",
            options: ["1 foot", "6 feet", "12-22 feet", "40+ feet"],
                answer: 1 },
        {question: "A water sample that is acidified must have a final water pH of?",
            options: ["<2.0", "<4.0", "<10.0", "<13.0"],
                answer: 0 },
        {question: "Radon is a radioactive decay daughter of radium 226.",
            options: ["TRUE", "FALSE", "na", "na"],
                answer: 0 },
        {question: "What water rights are acquired from diverting a water source and then putting it to beneficial use?",
            options: ["Riparian", "Directive", "Appropriative", "Human"],
                answer: 2 },
        {question: "What can be done to prevent discharge cavitation from occurring?",
            options: ["Place another pump on the line", "Lower the CO2 level", "Grease Bearings Annually", "Replace the fill lines"],
                answer: 0 },
        {question: "Reaching breakpoint chlorination means?",
            options: ["The chlorine demand has been met", "The amount of chlorine is excessive", "Chlorination is breaking pumps", "More Chlorine needs to be added"],
                answer: 0 },
        {question: "What is the maximum feed rate when adding fluoride to drinking water?",
            options: ["1.0 mg/L", "2.3 mg/L", "3.0 mg/L", "3.3 mg/L"],
                answer: 0 },
        {question: "What does the pulsating energy in a pulsator clarifier help to do?",
            options: ["Maintain a uniform sludge blanket layer", "Raise the sludge blanket over the weir for wasting", "Mix the coagulants with raw water", "Mix the coagulants and help with flocculation"],
                answer: 0 },
        {question: "A 50% solution of caustic soda will begin to crystallize if the temperature drops below?",
            options: ["32 Degrees Fahrenheit", "82 Degrees Fahrenheit", "54 Degrees Fahrenheit", "44 Degrees Fahrenheit"],
                answer: 2 },
        {question: "For maximum charge neutralization the average zeta potential should be in what range?",
            options: ["-90 to 0", "0 to +3", "-60 to -24", "-3 to -1"],
                answer: 1 },
        {question: "What should be determined first before an in ground sedimentation tank is drained?",
            options: ["Water Table Level", "The Solids Content", "The Hazardous Metals Content", "Sludge Volume and Volume of Process Area to Make Sure it will be Large Enough"],
                answer: 0 },
        {question: "What form is the protozoan Giardia Lamblia transmitted in?",
            options: ["United Form", "Constant Form", "Growth Form", "Cyst Form"],
                answer: 3 },
        {question: "The maximum amount of time that between draining, cleaning, and inspection of sedimentation basins with mechanical sludge removal components is?",
            options: ["Daily", "Bi-Weekly", "Monthly", "Annually"],
                answer: 3 },
        {question: "What sludge dewatering process requires a pre-coat of diatomaceous earth and its use has declined due to other newer methods?",
            options: ["Filter Press", "Belt Filter Press", "Vacuum Filters", "Centrifuge"],
                answer: 2 },
        {question: "If the chlorine demand suddenly increases from 0.4 mg/L to 2.8 mg/L, what could be the reason?",
            options: ["The water temperature is increasing", "The chlorinator is clogged", "Pollution", "Erratic well pump operation"],
                answer: 2 },
        {question: "A change in the water elevation from the normal level to the pumping level is?",
            options: ["Residual", "Drawdown", "Demand", "Flux Leveling"],
                answer: 1 },
        {question: "If the continuous monitoring of the residual disinfectant concentration of the water entering the water system fails, how often will an operator need to collect a grab sample until the problem is fixed?",
            options: ["Every 4hrs", "Every Hour", "Every 24hrs", "Every 1440 mins"],
                answer: 0 },
        {question: "What is the most probable solution if nematodes are interfering with the disinfectant?",
            options: ["Use chloramines", "Use oxygen deprivation", "Decrease detention time of finished water", "Optimize the settling process"],
                answer: 3 },
        {question: "If a body of water has high salinity and is warm, it will generally be high in dissolved oxygen.",
            options: ["TRUE", "FALSE", "na", "na"],
                answer: 1 },
        {question: "What sludge dewatering process is best for alum sludges when the cakes are very dry, filtrate is clear, and solids capture is very high?",
            options: ["Belt Filter Press", "Vacuum Filters", "Centrifuge", "Filter Press"],
                answer: 3 },
        {question: "Coliform bacteria are classified as?",
            options: ["Gram Neutral", "Grammerfication", "Gram Positive", "Gram Negative"],
                answer: 3 },
        {question: "What is the most efficient process for the removal of nitrate and nitrate?",
            options: ["Cation Exchange", "Anion Exchange", "Powered Activated Carbon", "Granular Activated Carbon"],
                answer: 1 },
        {question: "When using the lime soda ash process, it is impossible to produce water with a hardness of less than?",
            options: ["50 mg/L", "25 mg/L", "100 mg/L", "105 mg/L"],
                answer: 1 },
        {question: "Impurities found in water that do not come from plants or animals are",
            options: ["Inorganic", "Organic", "Viruses", "Cryptosporidium"],
                answer: 0 },
        {question: "One criteria to avoid filtration is that the fecal coliform concentration must be equal to or less than how many mg/L in representative samples of the source water immediately before the first or only point of disinfectant application in at least what percentage of the measurements made for the previous 6 months that the system served water to the public on an ongoing basis.",
            options: ["35/200 mL : 95%", "20/100 mL : 90%", "80/100 mL : 65%", "10/100 mL : 99%"],
                answer: 1 },
        {question: "To unclog the head of a chemical feed pump an operator should first?",
            options: ["Chizzle scale away", "Remove it then soak it in a weak solution of hydrochloric acid", "Remove and then replace with new one", "Turn up pump to break away blockage"],
                answer: 1 },
        {question: "Granular activated carbon is used as?",
            options: ["Kill Pathogens", "Disinfect Pathogens", "Filter Media to remove taste & odor causing agents", "Sterilize Water"],
                answer: 2 },
        {question: "What color will the water sample change when using amperometric titrator to check the chlorine residual?",
            options: ["Pink", "Red", "Purple", "None of the above"],
                answer: 3 },
        {question: "What is a physical separation between a water supply outlet and the flood-level rim of a receiving vessel that must be at least twice the diameter of the water supply outlet and the flood-level rim of the receiving vessel. This separation must be at leasttwice the diameter of the water supply outlet and never less than one inch?",
            options: ["Cross-Connection", "Air Gap", "Flushometer", "Fill Pipe"],
                answer: 1 },
        {question: "Why has magnetic ion exchange resin been developed?",
            options: ["To remove chlorides", "To remove total organic carbon", "To remove iron and magnesium", "To add pH"],
                answer: 1 },
        {question: "What is the usual detention time required to produce optimal floc aggregation?",
            options: ["30 seconds", "30 mins", "30 hours", "30 days"],
                answer: 1 },
        {question: "Gravity filters should not use more than what percent of daily production for backwash?",
            options: ["10-15%", "3-5%", "90-99%", "17-20%"],
                answer: 1 },
        {question: "Filtration rates vary from what of filter surface area?",
            options: ["40-45 GPM/sq ft", "1.15-2 GPM/sq ft.", "0.15-5 GPM/sq ft.", "15-23 GPM/sq ft."],
                answer: 2 },
        {question: "Waterborne diseases like typhoid and cholera are caused by?",
            options: ["Viruses", "E.Coli", "Bacteria", "Cryptosporidium"],
                answer: 2 },
        {question: "According to the Surface Water Treatment Rule, multiple barrier treatment is defined as?",
            options: ["Coagulation, Flocculation, Sedimentation, and Filtration", "Coagulation, Flocculation, and Filtration", "Removal by filtration and inactivation by disinfection", "Coagulation, Sedimentation, and Filtration"],
                answer: 2 },
        {question: "Adding CO2 to water will?",
            options: ["Raise the pH", "Lower the pH", "Will turn the water a reddish color", "No noticeable change"],
                answer: 1 },
        {question: "Vegetation control in and around reservoirs is practiced to control the release of chemical compounds that",
            options: ["Produce T-1000's", "Produce Biofilm", "Produce Viruses and Cryptocurrency", "Produce Byproduct Precursors"],
                answer: 3 },
        {question: "What is the most probable solution if crustaceans have clogged the water treatment plant's filters?",
            options: ["Shutdown one filter at a time and drain", "Backwash filters using high concentration of ozone", "Use a disinfectant that targets the specific organisms in question", "Shutdown the filters and physically removed them"],
                answer: 2 },
        {question: "What causes an increase in taste and odors when natural waters lack DO?",
            options: ["Anaerobic Decomposition", "Oxidation of Organic Material", "pH reduction causing an increase in Iron", "Increase in Algae Growth"],
                answer: 0 },
        {question: "Records of chemical analyses should be kept for?",
            options: ["1 Year", "5 Years", "10 Years", "No need to save"],
                answer: 2 },
        {question: "What chemical can be added to the water system to sequester Iron and Manganese?",
            options: ["Polyphosphates", "Chlorine", "Chloramines", "Aquaman"],
                answer: 0 },
        {question: "Lead contamination in drinking water may cause children to have altered physical and mental developments.",
            options: ["TRUE", "FALSE", "na", "na"],
                answer: 0 },
        {question: "The more hydroxide ions",
            options: ["The more basic the solution", "The more acidic the solution", "The more more hydroactive", "The more radioactive the solution"],
                answer: 0 },
        {question: "During daylight hours, algae growth in a reservoir will do what?",
            options: ["Decrease DO and pH levels", "Increase DO and pH levels", "Decrease pH only", "Increase pH only"],
                answer: 1 },
        {question: "Where do Enteropathogenic organisms in water supplies originate?",
            options: ["In the intestinal tract of warm blooded animals", "In the Air", "Occur during Freezing Temperatures", "Are Natural and should be of no Concern to the Operator"],
                answer: 0 },
        {question: "Evaporated water in the earth's atmosphere will condense to form",
            options: ["Oxygen", "Cloud Formations", "C02", "Mildew"],
                answer: 1 },
        {question: "The process by which water becomes a gas and rises is called?",
            options: ["Precipitation", "Evaporation", "Coagulation", "Stratification"],
                answer: 1 },
        {question: "The disinfection treatment process is?",
            options: ["The sterilization of pathogenic organisms", "The removal, deactivation or killing of pathogenic microorganisms", "The removal of THM's and TDS from the finished water", "The removal or sterilization of drinking water from harmful viruses and bacteria"],
                answer: 1 },
        {question: "Dissolved-Air flotation is particularly good for?",
            options: ["Removing Algae", "Removing Oxygen", "Adding Oxygen", "Removing Excess Copper Sulfate"],
                answer: 0 },
        {question: "What is a major cause of short circuiting in a sedimentation basin?",
            options: ["Improper Motor and Pump Alignment", "Loss of DC Power to sedimentation basin", "Influx from Capacitor", "Poor Inlet Baffling"],
                answer: 3 },
        {question: "What chemical oxidant would be best for controlling the forming of THMs?",
            options: ["Chloramines", "Chromium-6", "Potassium Permanganate", "Chlorine"],
                answer: 0 },
        {question: "The treatment process that controls corrosion or scaling is known as?",
            options: ["Stabilization", "Chlorination", "Rust Proofing", "CT Value"],
                answer: 0 },
        {question: "When the cell division in bacteria has been disrupted, it has been?",
            options: ["Killed", "Sterilized", "Disinfected", "Inactivated"],
                answer: 3 },
        {question: "If the natural fluoride content of raw water is variable, the concentration of the raw water should be measured?",
            options: ["Every 4hrs", "Every Day", "Once a Month", "Once on hottest day of the year and once on the coldest day of the year"],
                answer: 1 },
        {question: "What effect will caustic soda (NaOH)have on water?",
            options: ["Decrease the pH of the water", "Increase the pH of the water", "Recarbonate Water", "Decarbonate Water"],
                answer: 1 },
        {question: "Chloramination is?",
            options: ["Adding liquid chlorine to water", "Adding ammonia to chlorinated water", "Removing chlorine from water", "The process of adding chlorine gas to water"],
                answer: 1 },
        {question: "Water treatment chemicals are added based on?",
            options: ["Volume", "Concentration", "Time", "Weight"],
                answer: 1 },
        {question: "In a conventional treatment plant, primary coagulant compounds added to water during the falsh-mix step are?",
            options: ["Soda Ash, Chlorine, and Caustic Soda", "Aluminum Sulfate, Ferric Chloride, and Cationic Polymer", "Aluminum Sulfate, Ferric Chloride, and Chlorine", "Ferric Chloride, and Cationic Polymer and Soda Ash"],
                answer: 1 },
        {question: "What process is considered to best to remove color from water in a conventional surface water treatment plant?",
            options: ["Sedimentation", "Chlorimation", "Filtration", "Coagulation"],
                answer: 3 },
        {question: "Turbidity particles will settle more quickly and uniformly in a sedimentation basin when there is?",
            options: ["No short-circuiting", "A high pH", "A low pH", "Low THM's"],
                answer: 0 },
        {question: "Filter alum and polymer compounds are primarily",
            options: ["for increasing the pH of the finished water", "designed to settle colloids", "for suppling the flux capacitor with saturation", "All of the above"],
                answer: 1 },
        {question: "Why is water softening a part of the water treatment process?",
            options: ["So viruses are easier to inactivate", "Hard water will not sterilize as easily", "To add salt and minerals to filtered drinking water", "To reduce scale formation on pipes, valves, and fitting through ion exchange"],
                answer: 3 },
        {question: "What is used to prevent water from entering a gas chlorinator?",
            options: ["Check Valve", "Foot Valve", "Fusible Plug", "Backflow Assembly"],
                answer: 0 },
        {question: "A surface water treatment plant should have at least how many filtration beds?",
            options: ["1", "2", "3", "4"],
                answer: 1 },

<!-- 125 and up -->

        <!-- {question: "When the temperature of raw surface water drops significantly the flocculator paddle speed should be?", -->
            <!-- options: ["Decreased to avoid wear from mixing denser water", "Increased since denser water makes mixing more difficult", "Kept the same since the temps have no effect on the water", "Turned Off until chemical adjustments can be made"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "What is used as part of a sedimentation basin to allow a controlled flow of the supernatant to be collected and directed to the filter beds?", -->
            <!-- options: ["Launder", "Diverter", "Weir", "Bar Cage"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "According to the AWWA, the time period a filter should be used and then replaced is?", -->
            <!-- options: ["1-2hrs", "24-48hrs", "60-72hrs", "Once a week"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "The structure Diatomaceous Earth filters media is applied to is called?", -->
            <!-- options: ["Support System", "A Septum", "Weir", "Wear Structure"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "The maximum safe level of electrical current that will not have any long lasting health effects is?", -->
            <!-- options: ["120 Volts", "220 Volts", "440 milliamps", "20 milliamps"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "Where are samples taken for lead and copper?", -->
            <!-- options: ["At State approved sample locations", "At the consumer's tap", "At the treatment plant", "Farthest point in the water distribution system"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "What is a hypochlorinator used for?", -->
            <!-- options: ["To detect cl2 residual level", "To detect cl2 being fed into the water supply", "To dechlorinate", "Feed liquid chlorine into the water supply"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "The outlet of a forced ventilation system for a chlorinator room she be located?", -->
            <!-- options: ["12 ft from the floor", "12 inch from the floor", "2 inch from the floor", "2 ft from the floor"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What is a common mistake operators make in regards to flocculation is excessive flocculation time.", -->
            <!-- options: ["TRUE", "FALSE", "na", "na"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "How often should sedimentation basins with mechanical sludge removal equipment be drained and inspected?", -->
            <!-- options: ["Every Month", "Once a year", "Once a day", "Once every six months"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "Current regulations require that water treatment wastes be monitored?", -->
            <!-- options: ["Daily", "Monthly", "Annually", "Every 1-3 Years"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "Anaerobic conditions in reservoirs can cause what problem?", -->
            <!-- options: ["Hardness", "High Carbon", "Low THMs", "Fish Kills"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "What happens when there is high algae growth in a reservoir?", -->
            <!-- options: ["DO and pH Decrease while CO2 Increase", "DO and pH Increase while CO2 Decrease", "DO, pH and CO2 Decrease", "DO, pH and CO2 Increase"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "What form is Giardia most infectious?", -->
            <!-- options: ["Cyst", "Trophozoite", "Protozoan", "Gel"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "The size of Giardia in the trophozoite stage is approximately?", -->
            <!-- options: ["10-15 µm", "10-15 mm", "10-15 in", "10-15 ft"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What are the hair like appendages that Giardia trophozoites use to propel themselves through water are?", -->
            <!-- options: ["Mobility Nodes", "NTUs", "Proteins", "Flagella"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "What organism is associated with taste and odors?", -->
            <!-- options: ["Protozoa", "Oscillatoria", "Bacteria", "Membrane"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "What is the term that defines the calculation of a water plants physical property due wear and tear?", -->
            <!-- options: ["Usage", "Pump Curve", "Depreciation", "None of the Above"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "Water hardness is measured in equivalent amounts of?", -->
            <!-- options: ["Cl2", "Proteins", "TDS", "Calcium Carbonate"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "The most probable cause of a problem with a chlorinator is?", -->
            <!-- options: ["Too much Cl2 in system", "Clogged Ejector", "The Cl2 is too cold", "The Cl2 is too warm"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "Typically, how long is the flash mixing time in the coagulation process?", -->
            <!-- options: ["Several Minutes", "Several Seconds", "Several Hours", "Several Days"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "What are the four zones that divide a typical sedimentation basin?", -->
            <!-- options: ["Mixer, flux capacitor, accumulator, and settler", "Inlet, effluent, and outlet zone", "Inlet, settling, sludge, and outlet zone", "Mixer, reactor, accumulator, and settler"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What is an inorganic particle that is stabilized in water by attracting a layer of oppositely charged ions surrounded by a diffuse layer of counterions?", -->
            <!-- options: ["Electrochemical Particle", "Hydrophobic Particle", "Imbalanced Particle", "Flux Particle"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What is the main purpose for adding coagulant chemicals to raw water?", -->
            <!-- options: ["To Prevent the Formation of THMs", "To Increase the Chlorine Residual", "To Destabilize Colloidal Particles", "To Mix Ammonia with Carbon Sulfate"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "Which is a chemical used in water treatment as a coagulating chemical?", -->
            <!-- options: ["CaOCl", "HCl(O24)", "Al2(SO4)3", "H2SO4(AU)2"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "An organic particle that is stabilized by attracting a layer of water molecules to its surface is known as a?", -->
            <!-- options: ["Cablein", "Wonder Waal's", "Hydrophilic Particle", "Zeta Potential"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "If adequate surface area and detention time is provided in the sedimentation basin, what would the expected solids removal efficiency level be?", -->
            <!-- options: ["0.75", "0.85", "0.95", "1"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "Which process helps remove contaminants in water by causing them to cling to the surface of certain filter grains?", -->
            <!-- options: ["Adsorption", "Chlorination", "Chlorimation", "Tuberculation"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What oxidant has a potential of producing ClO3 by products?", -->
            <!-- options: ["Chlorine", "Chloramines", "Calcium Bichromate", "Chlorine Dioxide"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "When natural zeolites are used for softening and they have become exhausted from use, what chemical are they regenerated with?", -->
            <!-- options: ["HAAA5s", "HCL", "NaCl", "Cl2"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What determines whether or not colloidal sized particles in suspension repel each other, stay in suspension, or agglomerate and eventually settle?", -->
            <!-- options: ["Type of chemical bonding", "Magnitude of the charges", "Flow and temperature of the water", "Number of collisions"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "What parameter must be much better than conventional treatment basins in basins using tube and plate settlers?", -->
            <!-- options: ["Floc rate must be 2 to 3 times slower than conventional basins", "Floc must have good settling characteristics", "Floc rate must be 4 to 6 times slower than conventional basins", "Metals must be oxidized"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "To regenerate virgin greensand it must be soaked in the filter bed for several hours in a solution of chlorine containing?", -->
            <!-- options: ["100 mg'L Cl2", "200 mg'L Cl2", "250 mg'L Cl2", "300 mg'L Cl2"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "If there is gravel displacement in a filter bed from backwash rates with too high of a velocity, could eventually cause?", -->
            <!-- options: ["Bed Shrinkage", "Compaction of the Filter Media", "Loss of Media into the backwash troughs", "A sand boil"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "Virgin Greensand...", -->
            <!-- options: ["Does not regenerate", "Requires regeneration with potassium permanganate 2 hour soak with 30 grams KMnO4/ft3", "Requires regeneration with potassium permanganate 3 hour soak with 80 grams KMnO4/ft3", "Requires regeneration with potassium permanganate 1 hour soak with 60 grams KMnO4/ft3"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "If a filter is operating at a normal flow rate, its ability to trap flocculated particles is suspension is a function of?", -->
            <!-- options: ["Media Depth and Uniformity Coefficient", "Effective Size Multiplied by Uniformity Coefficient", "Media Depth and Media Size", "Effective Size Multiplied by Uniformity Coefficient Divided by the Media Size"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "Once they become fouled, how are reverse osmosis membranes cleaned?", -->
            <!-- options: ["They are cleaned with an acid wash", "They are cleaned with an acid, then with an industrial soap for 24hrs", "They are cleaned first with high purity soap and then soaked for 3 days in an acid solution", "They are soaked in high purity industrial soap for 24hrs"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What membrane process is used to treat brackish water or seawater?", -->
            <!-- options: ["Ultrafiltration", "Reverse Osmosis", "Nanofiltration", "Microfiltration"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "What is the process that is used to concentrate sludge?", -->
            <!-- options: ["Thickener", "Solar Lagoon", "Centrifuge", "Sand Bed"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What is the most troublesome operating problem for a sedimentation basin?", -->
            <!-- options: ["Short Circuiting", "Sludge Collection Removal", "Density Currents", "Algae and Slime Growths"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "When sludge is produced by water drawn from sources with relatively low turbidity it can be?", -->
            <!-- options: ["High in liquid content", "High in silt", "Handel like clay", "Very gelatinous and difficult to handle"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "When soda ash is added to water for softening purposes what will it do?", -->
            <!-- options: ["Raise the pH of water", "Decrease the pH of water", "Disinfect the water", "Decrease the CO2 in the water"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "A composite sample should never be collected for what type of analysis?", -->
            <!-- options: ["TDS", "Turbidity", "Bacteriological", "All of the Above"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "If a water system collects at least 40 samples per month for total coliform analysis, no more than 20% of samples can come back positive.", -->
            <!-- options: ["TRUE", "FALSE", "na", "na"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "When must a water system collect annual samples if the water system has been determined to be reliable by the State and consistently below the MCL level for organic compounds?", -->
            <!-- options: ["During the Winter", "During the Summer", "The first of every year", "During the quarter that previously yielded the highest analytical results"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "An operator must strike a balance between TOC removal and the", -->
            <!-- options: ["Disinfection By products rule", "Backwash Times", "Lead and Copper Rule", "Filter Backwash Recycle Rule"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What is the most important thing to consider in automatic startup after a power failure has occured?", -->
            <!-- options: ["The Process", "Water Quality", "Operator Safety", "Power Surges"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "Under the process of safety management, sites are required to do a site assessment if the facility in a single process has more than how many pounds of chlorine?", -->
            <!-- options: ["1,500lbs", "2,000lbs", "2,500lbs", "3,300lbs"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "Even a low concentration of ammonia gas can be fatal to humans if it is at least?", -->
            <!-- options: ["1 ppm", "500 ppm", "1,000 ppm", "2,000 ppm"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "What adverse effects does the secondary contaminant manganese have?", -->
            <!-- options: ["Corrosion", "Sewage Contamination", "High THMs", "Discolored laundry and changed taste of water"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "How much does water expand by when it freezes compared to its original value?", -->
            <!-- options: ["One-ninth", "One-seventh", "one-twelve", "one-tenth"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What is calcium sulfate also known as?", -->
            <!-- options: ["Limestone", "Gypsum", "Talc", "Dolomite"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "What is the simplest chlorine gas feeder for controlling chlorine gas flow?", -->
            <!-- options: ["Sonic Flow", "Induction Mixer", "Constant Differential Pressure", "Variable Differential Pressure"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "One ton chlorine containers are equipped with two valves, one for liquid and one for gas.", -->
            <!-- options: ["TRUE", "FALSE", "na", "na"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What does a low pH favor the formation of?", -->
            <!-- options: ["Total Trihalomethanes", "Haloacetic Acids", "Both Haloacetic Acids and Total Trihalomethanes", "Neither Haloacetic Acids and Total Trihalomethanes"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "When it is dissolved in water for disinfection purposes, how long does ozone last?", -->
            <!-- options: ["A few seconds to a few minutes", "30-45 mins", "1-3 hrs", "24hrs"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What does the saturation point of calcium carbonate primarily depend on?", -->
            <!-- options: ["TDS", "Temperature", "Calcium Concentration", "pH"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "How often should the fluoride concentration be measured in treated water?", -->
            <!-- options: ["Hourly", "Daily", "Weekly", "Monthly"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What type of chlorine gas feeder is most commonly used?", -->
            <!-- options: ["Pressure", "Combination Water and Pressure", "Vacuum", "Flux Capacitor"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "Which of the following composes the majority of scale in pipes?", -->
            <!-- options: ["CaCO3", "HCI", "CaSO4", "Ca(HCO3)2"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What would be best to use for corrosion inhibition if the water is very low in alkalinity and calcium concentration?", -->
            <!-- options: ["Chlorine", "Chloramines", "Sodium Hydroxide", "Polyphosphates"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "What is used for detection of chlorine gas leaks?", -->
            <!-- options: ["10% solution of ammonia sulfide", "10% solution of sulfuric acid", "10% solution of ammonia hydroxide", "10% solution of ammonia hyfluxide"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What device found in labs sterilizes by using pressurized steam?", -->
            <!-- options: ["Flux Capacitor", "Autoclave", "AutoZone", "Steamer"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "Coliform bacteria are always?", -->
            <!-- options: ["Harmful to Human Health", "Harmful to Human and Animal Health", "Present in the Natural Environment", "Harmful Only to Children and the Elderly"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What is the best type of salt to use in the regeneration of ion exchange softener resin?", -->
            <!-- options: ["Rock Salt or Pellet type Salt", "Chloride Salt or Grey Salt", "Dry Salt or Granular Salt", "Sea Salt or Table Salt"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "Which natural electrical force keeps colloidal particles apart in water treatment?", -->
            <!-- options: ["Ohms Law", "Zeta Potential", "AC/DC", "S&P 500"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "What chemical oxidant would be most effective for controlling biological growth?", -->
            <!-- options: ["UV", "Chlorine", "Ozone", "HAA5s"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "A method to increase or maintain the DO concentration of a thermally stratified reservoir?", -->
            <!-- options: ["Adding Copper Sulfate", "Destratification and Hypolimnetic Reaeration", "Adding Bluestone", "Adding Alum"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "The ion exchange process usually is used to remove what from water?", -->
            <!-- options: ["Sodium Thiosulfate", "Chlorine", "Iron and Magnesium", "Calcium and Magnesium"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "A total coliform positive sample must be tested for the presence of?", -->
            <!-- options: ["Chlorine", "THMs", "Giardia lamblia", "Fecal Coliforms (E.coli)"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "What is the definition of decant?", -->
            <!-- options: ["To draw off a liquid layer from a vessel of any size without disturbing any layers above or below", "To draw off the sediment at the bottom of a vessel of any size without disturbing the overlying liquid layer", "To remove the precipitate at the bottom of any size vessel", "To draw off the liquid from a vessel of any size without stirring up bottom sediment"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "The backwash rate must be high enough to?", -->
            <!-- options: ["Prevent media loss and allow the operator to observe the media", "Provide for proper bed expansion", "Expand the media to reach fluidization and cause the grains to agitate violently", "All of the above"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "Which of the following are true. At the end of the coagulation, flocculation, and sedimentation process?", -->
            <!-- options: ["Over 90% of colloidal sediment is removed", "A significant percentage of bacteria and protozoa are removed", "Color is removed", "All of the Above"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "The continuous circulation of water from the earth into the atmosphere and back again is called?", -->
            <!-- options: ["Hydrologic Cycle", "Evaporation Cycle", "Hydraulic Cycle", "Paleo Cycle"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What causes water to turn red?", -->
            <!-- options: ["Fluoride", "Iron", "Bacteria", "HAA5s"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "What is the principle form of alkalinity found in raw water from both surface and ground sources?", -->
            <!-- options: ["Fluoride", "Alum", "Calcium Bicarbonate", "Hydrochloric Acid"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "A pump should always be insatlled?", -->
            <!-- options: ["Inline with a chlorine ejector", "Parallel with a chlorine ejector", "Downstream of a chlorine ejector", "Upstream of a chlorine ejector"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "What TON will consumers start to notice?", -->
            <!-- options: ["1", "2", "3", "36"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "Coagulation is a chemical and physical reaction that converts?", -->
            <!-- options: ["Cl2 into Chloramines", "Sodium into Salt", "Non Settled Solids into Settable Solids", "Hydrogen into Oxygen Concentrate"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "Alachlor, Lindane, and Toxaphene are examples of?", -->
            <!-- options: ["VOCs", "DPBs", "SOCs", "IOCs"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What units ae the MCLs for radium-226, radium 228 and gross alpha particles radioactivity measured in?", -->
            <!-- options: ["Ounces", "mg/L", "pCi/L", "ppm"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "The acronym BAT stands for", -->
            <!-- options: ["Below Average Temp", "Beta Atom Technology", "Best Available Technology", "Be At Timeline"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "A grout seal should be?", -->
            <!-- options: ["Installed 12 in from the floor", "Have a backflow isntalled on it", "Requires Screen Bars to keep rodents out", "Filled with cement grout to a minimum of 10 ft down"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "What will occur if the activation process of silica is not carefully controlled?", -->
            <!-- options: ["In could inhibit floc formation", "The silica could splash due to high heat of reactants", "It could deposit silica on the flocculators and the gears", "It could corrode and destroy the metal and rubber in the flocculators"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "The monitoring program that checks for Benzene (Leaking Underground Storage Tank) is checking for what kind of chemical contaminant?", -->
            <!-- options: ["DOs", "VOCs", "DBPs", "NBAs"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "What changes does an operator need to make when there are issues with floc formation?", -->
            <!-- options: ["Adjust Coagulant Dosage", "Change Coagulant Type", "Adjust Flocculator Mixing Intensity", "All of the above"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "Why is turbidity in drinking water undesirable?", -->
            <!-- options: ["It provides a medium for the transmission of pathogens in drinking water", "Can turn drinking water varying colors", "Can cause odor complaints", "Causes aesthetic issues in water which will results in complaints"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "At what temperature does the maximum density of water occur?", -->
            <!-- options: ["-4.0 Degrees Celsius", "4.0 Degrees Celsius", "0.0 Degrees Celsius", "0.04 Degrees Celsius"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "Monthly sampling results must be reported by the water purveyor?", -->
            <!-- options: ["Daily", "One the 1st of each month", "Every 12 months", "Within the first 10 days of the month following the month in which the samples were taken"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "Where is sludge pumped when it is removed from a clarifier or after a filter backwash?", -->
            <!-- options: ["Sewer", "Into a settling pond", "Drain to city for cleaning", "Back into the system"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "Why do mud balls and hard spots develop in high rate gravity filters during the summer months?", -->
            <!-- options: ["The heat makes the water too had and then gets sticky", "The flow is too low because of lack of raw water", "The water becomes too hard and effects the filters", "Sedimentation is not as good in the summer months because the flows are higher and more floc is imbedded onto the filters"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "In what form is Iron soluble in water?", -->
            <!-- options: ["Ferrous Iron", "Iron Hydroxide", "Iron Oxide", "Ferric Iron"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "A constituent dissolved in source water that will precipitate when oxidized is?", -->
            <!-- options: ["Ferrous Iron", "Sulfide", "Hydrogen Peroxide", "NaCI"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What laboratory device sterilizes laboratory apparatuses and microbial media by using pressurized steam?", -->
            <!-- options: ["Oven", "Totalizer Steamer", "Autoclave", "Flux Capacitor"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What type of self-contained breathing apparatus should be used at water plants?", -->
            <!-- options: ["Power Suit", "Positive-Pressure", "Self Breathing", "Extra Large"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "Salts, Bases, and Acids lacking carbon are organic compounds.", -->
            <!-- options: ["TRUE", "FALSE", "na", "na"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "If a water system collects less than 40 samples a month, how many can be coliform positive and the water system still maintain compliance?", -->
            <!-- options: ["1", "5", "0.05", "12"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "The maximum sustained flow possible from a well mostly depends on?", -->
            <!-- options: ["Local & State Restrictions on Pumping", "Porosity and Permeability of the Aquifer", "The amount of surface water in the general area", "The size of the distribution pumps feeding the water system"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "Monochloramines are?", -->
            <!-- options: ["Responsible for the formation of THMs", "Increase the chance of harmful DBPs being created in treated water", "Highly powerful and cause taste & odor complaints when used", "Less powerful and higher residuals are required compared to free Cl2"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "Most totalizer meters at treatment plants are commonly", -->
            <!-- options: ["Positive Displacement", "Venturi", "Impeller", "Compound"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What forms when you add Alum to turbid water?", -->
            <!-- options: ["THMs", "Floc Particles", "T-10000's", "Volumetric Solids with granular particles"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "What chemical may encourage growth of algae and microorganisms?", -->
            <!-- options: ["Sulfuric Acid", "Zinc Orthophosphates", "Chlorine", "Chloramines"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "Which is the best removal method if a well contains soluble iron?", -->
            <!-- options: ["Install a manganese greensand filter and regenerate with potassium permanganate using a chemical feeder", "Adjustment to Cl2 Feed", "Add Filters", "Increase Filter Runs"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What part of the human body is the most vulnerable to allowing microorganisms to enter it?", -->
            <!-- options: ["Stomach", "Throat", "Heart", "Eyes"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "Coagulation occurs during the first", -->
            <!-- options: ["10-15 mins", "45-55 seconds", "1 to 5 seconds", "2-3 minutes"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "If ammonia vapor is passed over a chlorine leak in a cylinder valve, the leak is indicate by", -->
            <!-- options: ["Alarms will go off", "Yellow/Greenish Cloud", "White Cloud", "Water will evaporate"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "Community water systems must check the natural radioactivity in their water supply at least?", -->
            <!-- options: ["Once a day", "Once a month", "Once a year", "Once every four years"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "When using chloramines", -->
            <!-- options: ["Chlorine is added first and then add ammonia", "Ammonia is added first and then chlorine", "Never add ammonia to chlorine", "Chloramines is added to ammonia"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "Direct filtration eliminates what conventional treatment step?", -->
            <!-- options: ["Flocculation", "Sedimentation", "Aeration", "Oxidation"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "What percentage of solids sludge is produced in the precipitative softening plant?", -->
            <!-- options: ["0.05", "0.1", "0.35", "0.5"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "The sampling points located for required sampling of natural radionuclides are located?", -->
            <!-- options: ["Consumer's Faucet", "Farthest point in the distribution system", "Representative points in the distribution system", "Each entry point to the water system"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "What percentage of the earth's surface is covered in water?", -->
            <!-- options: ["0.22", "0.52", "0.61", "0.71"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "What is the pH range of sodium hypochlorite?", -->
            <!-- options: ["4.0 to 6.0 pH units", "5.0 to 5.3 pH units", "9.0 to 11.0 pH units", "13.0 to 14.0 pH units"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "Free chlorine residual values are based on contact time of at least?", -->
            <!-- options: ["1-5 seconds", "1 min", "10 mins", "24hrs"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "Reservoir turnover events cause by temperature changes reduce what at deeper water levels?", -->
            <!-- options: ["Cl2", "O2", "TDS", "Flocculation"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "Potassium Permanganate should be?", -->
            <!-- options: ["Frozen", "Fed before chlorine", "Heated", "used with powered activated carbon"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "What does it mean if there are sand boils on the surfaces of rapid sand filters during backwash?", -->
            <!-- options: ["There is not enough backwash water being reused and the operator should use raw water", "The backwash valves are being opened too quickly", "The Flux Capacitor is Clogged", "All of the above"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "The loss of chloramine residuals in a water line or a storage tank is due to?", -->
            <!-- options: ["Not enough ammonia usage", "The DO levels are too low", "Nitrification and an increase in heterotrophic bacteria levels", "Hardness of water is too high"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "Where does most of the carbon dioxide in groundwater originate from?", -->
            <!-- options: ["Plant Respiration", "Animal Respiration", "Biological Oxidation of Organic Matter", "Weathering of Rocks"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What does pinpoint floc, fish eyes, and high turbidity in settled water indicate?", -->
            <!-- options: ["Operating problems and need further investigation", "Not enough pump power", "Perfect operating", "Low ammonia"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "When treating surface water, the main reason for removing solids is?", -->
            <!-- options: ["To ensure turbidity levels are less than 0.3 NTU", "Lower Cl2 Usage", "Increase DO", "Keep a stabilized pH"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What is a universal solvent?", -->
            <!-- options: ["Water", "Caustic Soda", "Sodium", "Methane"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "The porous material just above the water table that holds small quantities of water by capillary action is called?", -->
            <!-- options: ["Capillary Fringe", "Alluvial", "Spring", "Venturi"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "A sedimentation basin with mechanical sludge removal equipment should be drained and inspected?", -->
            <!-- options: ["Once a week", "Once a month", "Once a year", "Once every two years"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What is the MCL for HAA5s?", -->
            <!-- options: ["0", "0.040 mg/L", "0.060 mg/L", "0.080 mg/L"], -->
                <!-- answer: 2 }, -->

<!-- 250 and up -->

        <!-- {question: "Recovered backwash water from a conventional surface water filtration plant may be returned to the headworks if allowed under?", -->
            <!-- options: ["Title 17", "Filter Backwash Recycle Rule", "Title 22", "Surface Water Treatment Rule"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "The action level for copper is 0.015 mg/L.", -->
            <!-- options: ["TRUE", "FALSE", "na", "na"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "One of the ways an optimum coagulant dosage can be established is?", -->
            <!-- options: ["Performing a DPD Test", "Performing a Jar Test", "Performing a Multiple Choice Test", "Observing Filter Run Times"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "Shellfish grown in polluted waters have been known to contain the organism that causes infectious hepatitis.", -->
            <!-- options: ["TRUE", "FALSE", "na", "na"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "In a saturator tank for flows of less than 100 gpm, how thick should the layer be maintained of sodium fluoride crystals?", -->
            <!-- options: ["6 inches", "11 inches", "1 foot", "3 feet"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What is the MCL for THM's?", -->
            <!-- options: ["80 mg/L", ".80 mg/L", "0.080 mg/L", "8.0 mg/L"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "The organism that causes Giardiasis", -->
            <!-- options: ["Easily taken care of with chlorine", "Are only a concern if there are animals drinking from your source water", "Are best controlled by filtration followed by disinfection", "Are too small to be filtered"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What range of temperatures will fusible plugs on chlorine cylinders melt?", -->
            <!-- options: ["147 to 152 degrees Fahrenheit", "157 to 162 degrees Fahrenheit", "155 to 159 degrees Fahrenheit", "167 to 171 degrees Fahrenheit"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "The release of dissolved gasses in saturated cold water when pressure decreases in filter beds causes?", -->
            <!-- options: ["Long Filter Runs", "Slime Growth", "Air Binding", "Possible Loss of Electricity"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "Anionic polymers are used as filter aids to agglomerate small floc particles left in the sedimentation basin effluent and make them tougher to avoid?", -->
            <!-- options: ["Drowning", "Hovering", "Shearing", "Changing pH"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "Chlorine gas will?", -->
            <!-- options: ["Support Combustion", "Burn in the presence of oxygen and moisture", "Conduct Electricity", "All of the above"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "Never install a new gasket when a chlorine cylinder or container is changed.", -->
            <!-- options: ["TRUE", "FALSE", "na", "na"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "What chemical could cause pink water problems?", -->
            <!-- options: ["DPD", "Chloramines", "Bromine", "Potassium Permanganate"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "The more hydrogen ions", -->
            <!-- options: ["The more basic the solution", "The more acidic the solution", "The more more hydroactive", "The more radioactive the solution"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "Which of the following illnesses is it hardest to kill the organism that causes the illness?", -->
            <!-- options: ["Infectious Hepatitis", "Cryptosporidiosis", "Cholera", "Typhoid"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "What zone in a lake or reservoir has weeds that grow underwater that may cause taste & odor complaints?", -->
            <!-- options: ["Coral Zone", "Littoral Zone", "Seagrass Zone", "Fun Zone"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "River water is not uniform in quality from hour to hour or day to day.", -->
            <!-- options: ["TRUE", "FALSE", "na", "na"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "As the level of phosphates increase in a new water supply, an operator should?", -->
            <!-- options: ["Increase chlorine dosage and check the pH", "Check the Hazen Williams Levels", "Increase the coagulant dosage and check for algae growth", "Shut the plant down immediately and check all filters"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "Compared to disinfecting water with free chlorine, what is a disadvantage in switching to ozone?", -->
            <!-- options: ["Increases water hardness", "Only can be done with well water", "Lack of a persistent residual", "Not reliable"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "For surface water systems without filtration, the Surface Water Treatment Rule requires public water systems to", -->
            <!-- options: ["Add extra Cl2", "Take Cl2 residual every 4 hours", "Notify consumers monthly until filtration is installed", "Maintain a CxT Value above the minimum value"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "What chemical oxidant is most effective in reducing the concentration of taste and odor compounds caused by actinomycetes species?", -->
            <!-- options: ["Potassium Permanganate", "Chloride Dioxide", "Peroxone", "Chloramines"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "Viruses are sometimes resistant to disinfection.", -->
            <!-- options: ["TRUE", "FALSE", "na", "na"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "How often should the solids concentration be determined in solid contact basins with fairly constant water quality parameters?", -->
            <!-- options: ["At least twice a day", "At least once a week", "At least once a month", "Quarterly"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What does it mean when a filter is ripening?", -->
            <!-- options: ["Entering its end of use and ready for backwash", "Becoming more efficient in particle removal", "Becoming ready to replace", "Becoming ready for consumption"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "What does not pose a threat to human health in the drinking water?", -->
            <!-- options: ["Nitrates", "Iron", "THMs", "All of the above"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "The factors that effect coagulation and flocculation with alum are", -->
            <!-- options: ["pH, turbidity, temperature, alkalinity, and hardness", "pH, turbidity, temperature, alkalinity, and corrosiveness", "pH, turbidity, temperature, alkalinity, and stirring speed", "pH, turbidity, and temperature"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What factor is used to express the relative volatility of a substance?", -->
            <!-- options: ["Henry's Constant", "Boyle's Law", "Chaitin's Constant", "Feigenbaum Constant"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What test is used to estimate the optimum dosage of chemical compounds used for some process in water treatment?", -->
            <!-- options: ["Taste Test", "Jar Test", "Star Test", "Volumetric Test"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "What organism can escape coagulation and then pass through a granular filter?", -->
            <!-- options: ["Cryptosporidium", "Giardia", "Naegleria", "Entamoeba"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "Which is the most persistent protozoa?", -->
            <!-- options: ["Trapezoid", "Cryptosporidium Parvum", "Giardia", "Cryptocurrency Parvum"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "Which is the normal sequence of solids removal processing following flash mixing in a conventional water treatment plant?", -->
            <!-- options: ["Coagulation, Flocculation, Sedimentation, Filtration and Chlorination", "Flocculation, Coagulation, Sedimentation, and Filtration", "Filtration, Flocculation, Coagulation, and Sedimentation", "Coagulation, Flocculation, Sedimentation, and Filtration"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "Backflow wash flows should expand filter media by?", -->
            <!-- options: ["10-25% of Normal", "32-44% of Normal", "30-50% of Normal", "100% of Normal"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What should the turbidity of settled water be before it is applied to the filters, post sedimentation process?", -->
            <!-- options: ["1 to 2 ntu", "2 to 4 ntu", "5 to 7 ntu", "11 ntu"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What is potassium permanganate most effective in?", -->
            <!-- options: ["Removing Color", "Removing THMs", "Removing Iron", "Removing Chlorine"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "Bar screens are used to?", -->
            <!-- options: ["Remove Debris", "Keep out trespassers", "Keep out bugs", "Hold filters in place"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "Why are check valves installed in suction lines?", -->
            <!-- options: ["To prevent treated water from entering the raw water flow", "To prevent a cross connection", "Minimize pump priming problems", "So the water does not enter the treatment plant unless the pump is running"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "Wet activated carbon will remove what from the air? (In regards to safety)", -->
            <!-- options: ["Oxygen", "Organic Gasses and Sulfide", "Carbon Dioxide", "Carbon Monoxide"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "When 0.3 mg/L chlorine is added to water, the residual will increase by 0.3 mg/L.", -->
            <!-- options: ["TRUE", "FALSE", "na", "na"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What process would be most effective for the destruction of heterotrophic bacteria?", -->
            <!-- options: ["Treat with Lime", "Treat with Soda Ash", "Temperatures higher than 160 degrees Fahrenheit", "Freeze and then let sit for more than 24hrs"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What test is used to determine the presence of coliform bacteria?", -->
            <!-- options: ["DPD", "Physical", "Presumptive", "Multiple Choice"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What one of these would be the best chemical oxidant to use for controlling THMs formation potential?", -->
            <!-- options: ["Potassium Permanganate", "Chloramines", "Chlorine Dioxide", "Oxygen"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What is the purpose of body feed in the operation of a diatomaceous earth filter?", -->
            <!-- options: ["To decrease the chlorine demand", "To increase the heavy metal count", "To provide longer filter runs", "To feed fluoride into the system naturally"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "Improper backwashing of the filter media can lead to?", -->
            <!-- options: ["Mudball Formation", "Improper SCADA Readings", "Clogging of Coffee Machine", "Getting Fired"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "For alum coagulation of color, what is the correct pH?", -->
            <!-- options: ["0.0-3.0", "1.1-3.2", "4.0-6.0", "7.2-9.4"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "A system that fails to collect water samples in their distribution system would fall under which public notification system?", -->
            <!-- options: ["Tier I", "Tier II", "Tier III", "No Need to Notify"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What is the next test when the membrane filter test shows four green colored colonies after incubating for 24hrs?", -->
            <!-- options: ["Incubate for an additional 24hrs", "Confirm by testing for E. coli and fecal coliform bacteria", "Place sample in autoclave for 15 mins", "None of the Above"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "An autoclave will sterilize at", -->
            <!-- options: ["With steam at 100 degrees Celsius at 25psi", "With steam at 300 degrees Celsius at 150psi", "With steam at 121 degrees Celsius at 15psi", "With steam at 100 degrees Celsius at 150psi"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What is the best process for sequestering manganese?", -->
            <!-- options: ["Polyphosphates Alone", "Polyphosphates and Chlorine", "Sodium", "Sodium Silicate"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "What is the minimum angle that self cleaning tube settlers must be placed?", -->
            <!-- options: ["10 degrees", "45 degrees", "50 degrees", "90 degrees"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "Ozone Generators", -->
            <!-- options: ["Must be supplied with extremely dry air", "Must be supplied with extremely wet air", "Must be supplied with extremely cool air", "Must be supplied with extremely solid air"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What is the best disinfectant against Cryptosporidium?", -->
            <!-- options: ["Chlorine", "Ozone", "Chloramines", "All of the Above"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "What type of algae would most likely be found in nutrient rich water?", -->
            <!-- options: ["Blue-green Algae", "Green Algae", "Brown Algae", "Diatoms"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "The hydrologic cycles create what two primary sources of water?", -->
            <!-- options: ["Distilled & Sterilized", "Ocean & River", "Springs & UV", "Ground & Surface"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "What are the precursors to THMs?", -->
            <!-- options: ["pH and Ammonia", "Natural Organics and Chlorine", "Acids and Borane", "Oil and Vinegar"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "How is chlorine dioxide formed?", -->
            <!-- options: ["H+2+O", "HCl+H2SO4", "Cl2+2NaClO2", "O+HCL"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "According to the AWWA, at 0.1 NTUs filtration can remove what percent of giardia cyts?", -->
            <!-- options: ["0.99", "0.25", "0.75", "0.01"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "Community and non-transient community water systems must test for what if they use ozone for disinfection of oxidation?", -->
            <!-- options: ["THMs", "pH", "Bromate", "Chlorine Residual"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "When a permit is required to enter a confined space, who may sign the permit?", -->
            <!-- options: ["Local or State Authority", "Entry Supervisor", "City Manager", "USEPA"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "What water quality indicator is of greatest concern in a surface water treatment plant?", -->
            <!-- options: ["Turbidity", "pH", "Residual", "Temperature"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What type of polymers are sometimes formulated with regulated substances?", -->
            <!-- options: ["Polyethylene", "Polypropylene and Polyethylene", "Divinylbenzene", "Nonionic and Anionic Polymers"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "Nitrification in the distribution system can best be described as?", -->
            <!-- options: ["The warming and cooling of the water in the actual water mains", "Oxidation of ammonia to form nitrite and nitrate", "The basic condition of hydrogen ions in the water system", "The changing of cells in pathogens during the treatment process into the distribution system"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "When should polyphosphates used for sequestration of iron and manganese from a well be injected?", -->
            <!-- options: ["Right After the Water Leaves the Well", "Before the Water Leaves the Well", "Inside the Well", "In the Storage Tank"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What chemicals are used to substitute chlorine as pre-oxidants to minimize the formation of disinfection byproducts in a water plant?", -->
            <!-- options: ["Polyphosphates, chlorine, fluoride", "Radiation, UV, and Hazen", "Ozone, chlorine dioxide, and potassium permanganate", "Soda-Ash, Chlorine, and Silver"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "Most regulated contaminants in drinking water?", -->
            <!-- options: ["Only Change the Taste & Odor of the Water", "Are Immediately Dangerous to Human Health", "Are Immediately Dangerous and Change the Taste of the Water", "Cause Health Effects Only After Long Exposure"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "What are different types of media used to filter water for human consumption?", -->
            <!-- options: ["Sand", "Diatomaceous Earth", "Garnet", "All of the above"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "What makes chlorine use more advantageous over chloramines?", -->
            <!-- options: ["It is a much stronger oxidant", "It has a longer history of use", "It has a more persistent residual", "It is easier to use"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What is the pH of a saturated solution of sodium fluoride?", -->
            <!-- options: ["4.2", "6.4", "7", "9.2"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What method can be used to control scaling, but is never used to control corrosion?", -->
            <!-- options: ["Galvanic Covering", "Electrodes", "Sequestering", "Chlorinating"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "How often should the fluoride feed system be checked?", -->
            <!-- options: ["Every Hour", "Every 24hrs", "Every Week", "Every Month"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What is true about heterotrophic bacteria?", -->
            <!-- options: ["Heterotrophic bacteria are non-coliform growths which may suppress growth of coliform bacteria", "The organisms utilize organic carbon as a food source", "Heterotrophic bacteria are enumerated by a heterotrophic plate count at the end of 48hrs", "All of the above"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "Acid rain is caused by", -->
            <!-- options: ["The mixing of precipitation and certain gases in the atmosphere", "Hydraulic Cycle", "Acid Evaporation", "Teslas"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What is the best process for removing turbidity?", -->
            <!-- options: ["Coagulation & Flocculation", "Sedimentation", "Filtration", "All of the Above"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "When responding to a chlorine gas leak, the responder should have a SCBA and a?", -->
            <!-- options: ["Level A Suit", "Level B Suit", "Superman Suit", "Swim Suit"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What type of pump is most commonly used to feed chemicals into a water supply?", -->
            <!-- options: ["Positive Displacement Pump", "Hand Pump", "Centrifugal Pump", "Packing Gland Pump"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "The actions levels for lead and copper are?", -->
            <!-- options: ["0.0015ppm & 1.3ppm", ".15ppm & .13ppm", "0.015ppm & 1.3ppm", "1.5ppm & .13ppm"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "In order to prevent air binding in a rapid sand filter, head loss should never exceed?", -->
            <!-- options: ["1 Foot", "10 Feet", "The receiving vessel", "The static head above the filter media"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "What is dissolved air flotation good for removing?", -->
            <!-- options: ["Acids", "Color", "Iron and Manganese", "Algae"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "The chemical combination for substances in solution so as to cause separation in the insoluble form can be described as?", -->
            <!-- options: ["Coagulation", "Stabilization", "Saturation", "Precipitation"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "What does the operator use to adjust the amount of liquid or gas delivered to water?", -->
            <!-- options: ["Pump", "Rotameter", "Needle Valve", "Pinch Valve"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "What is the removal level of cryptosporidium oocysts with conventional sedimentation?", -->
            <!-- options: ["Less than 0.5 Log", "1 Log", "2 Log", "3 Log"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "Regulations require that wastes from water treatment be monitored?", -->
            <!-- options: ["Daily", "Weekly", "Monthly", "Annually"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "The type of filter that provides the lowest flow per square foot of surface are is?", -->
            <!-- options: ["Slow Sand Filter", "Chlorimation", "DPB", "THM"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What emergency kit is for chlorine tank cars?", -->
            <!-- options: ["Kit A", "Kit B", "Kit C", "Kit D"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What conventional treatment step is eliminated by direct filtration?", -->
            <!-- options: ["Coagulation", "Flocculation", "Sedimentation", "Filtration"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "Giardia Lamblia is transmitted?", -->
            <!-- options: ["In Light", "In Cyst Form", "By Touch", "In Air"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "Ion exchange processes can typically be used for direct groundwater treatment as long as turbidity and what else have levels that are not excessive?", -->
            <!-- options: ["Sodium Sulfate", "Carbon Dioxide", "Iron", "Calcium Carbonate"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "Which is classified as a secondary contaminant?", -->
            <!-- options: ["pH", "Iron", "Red or Brown Water", "All of the above"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "Ozone contractors must have a system to collect ozone off-gas because?", -->
            <!-- options: ["Ozone can be used to create more energy to run plants", "Ozone is expensive and it can be reused", "Ozone is taxed if it is released into the atmosphere", "Ozone is toxic"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "When filter run times between backwashes are long, like one week, because low turbidity water is being applied to the filters, what problem could still arise?", -->
            <!-- options: ["Air Binding and Formation of Mudballs", "Air Binding", "Floc Breakthrough", "Mudball Formation"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "In gram staining, part of the coliform verification is?", -->
            <!-- options: ["Completed Test", "Jar Test", "Presumptive Test", "Confirmed Test"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "All chlorine gas rooms...", -->
            <!-- options: ["Should have lights and fans on the inside and wired to the same switch", "Should have a window in the door so an operator can look into the room to detect any abnormal conditions", "Be fitted with chlorine resistant power exhaust fans ducted out at ceiling level", "Should have sealed walls and doors that open inward"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "Protozoa are larger than bacteria which are larger than viruses.", -->
            <!-- options: ["TRUE", "FALSE", "na", "na"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "At its endpoint, what color does the oxidant potassium permanganate turn?", -->
            <!-- options: ["Red", "Pink", "Reddish-brown", "Yellow"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "Notification to the public of a Tier III violation is done", -->
            <!-- options: ["Within 24hrs", "Within 48hrs", "Notify within 12 months usually in the CCR", "Never Tell the consumers because it will cause irrational fear"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "Water impurities that come from plants or animals are", -->
            <!-- options: ["Giardiasis", "Cryptocurrency", "Inorganic Carbon", "Organic Carbon"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "Which of these has the most impact on tastes and odors in water?", -->
            <!-- options: ["H2Cl4", "HOCI", "NCI3", "NH2CI"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "Impurities that do not dissolve in water and settle out eventually are?", -->
            <!-- options: ["Viruses", "Settlable Solids", "Carbon Extractual", "Non Carbon Extractual"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "The pH scale ranges from?", -->
            <!-- options: ["0-12", "45671", "0-14", "45669"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "By what factor does the hydrogen ion concentration change when the pH changes from 8.0 to 9.0?", -->
            <!-- options: ["1", "10", "100", "0.1"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "Water that is softened has a high pH and a high concentration of CaCO3. Therefore stabilization is essential in order to prevent the CaCO3 from precipitating out on?", -->
            <!-- options: ["Household Plumbing", "The clear well", "The filters", "Distribution Pipes"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What conditions in a gravity filter will be produced when there is a larger particle size and less dense anthracite media?", -->
            <!-- options: ["Longer filter runs and a reduced filtration rate", "Reduced filter runs and a reduced filtration rate", "Longer filter runs and a greater filtration rate", "None of the above"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "Pulsator clarifiers are used to?", -->
            <!-- options: ["Treat water that is high in color and high in turbidity", "Treat water that is high in color and low in turbidity", "Treat water that is low in color and low in turbidity", "Treat water that is low in color and high in turbidity"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "Where are the two points on a gravity filter used to measure head loss located?", -->
            <!-- options: ["At the water level and at the filter outlet", "At the sand level and at the water level", "At the filter inlet and the basin", "At the filter outlet and inlet"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "Every year there are approximately what percentage of confined space deaths of would be rescuers?", -->
            <!-- options: ["0.05", "0.5", "0.67", "0.99"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "A chlorine evaporator maintains a water bath at?", -->
            <!-- options: ["158-165 Degrees Fahrenheit", "170-180 Degrees Fahrenheit", "188-223 Degrees Fahrenheit", "250-334 Degrees Fahrenheit"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "What is the quantity of dissolved oxygen in water a function of?", -->
            <!-- options: ["Temperature, Pressure, and Salinity", "Temperature and Alkalinity", "pH and Temperature", "pH, Alkalinity, Temperature, and TDS"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "The marble test is used to determine if water is saturated with calcium carbonate and has what other general use?", -->
            <!-- options: ["To check the stability of water softened in the lime soda ash process", "To indicate alkalinity levels", "To make pH adjustments", "All of the Above"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "How much carbon is approximately lost during the reactivation process for granular activated carbon?", -->
            <!-- options: ["0.05", "0.08", "0.24", "0.68"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "Every 1.0 mg/L of alum consumes what amount of alkalinity during the formation of floc particles?", -->
            <!-- options: ["0.5 mg/L", "1.0 mg/L", "2.0 mg/L", "2.5 mg/L"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "Why do operators monitor a filter's operation time, headloss and effluent turbidity level?", -->
            <!-- options: ["To watch for Breakpoint Chlorination", "Identify when it is time to do a filter backwash", "To measure pump curve", "Identify when a filter is bad and needs to be permanently replaced with a new filter"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "What is a similar process to reverse osmosis that uses lower pressures without removing all mineral content?", -->
            <!-- options: ["Ninafiltration", "Ninofiltratin", "Nitrification", "Nanofiltration"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "The Marble test is associated with?", -->
            <!-- options: ["CaCO3 Saturation", "Presents or Absence", "Positive or Negative", "THM's Formation"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "Which oxidant has the protentional of producing Chlorate (Cl03) by-products?", -->
            <!-- options: ["Ozone", "Chlorine Dioxide", "Sulfuric Oxide", "Nitric Acid"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "Assuming all other variables remain the same, a decrease in the pH when using free chlorine would?", -->
            <!-- options: ["Increase the C . T required and decrease the inactivation ratio", "Increase the C . T required and increase the inactivation ratio", "Decrease the C . T required and Decrease the inactivation ratio", "Decrease the C . T required and increase the inactivation ratio"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "The most favorable condition in raw water for good flocculation with alum is?", -->
            <!-- options: ["Low pH - Low Alkalinity", "High pH - Low Alkalinity", "High pH - High Alkalinity", "Low pH - High Alkalinity"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "What water quality indicator should be considered in a lake de-stratification program?", -->
            <!-- options: ["Dissolved Oxygen Levels", "Chlorine Residual", "Drawdown", "All of the above"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What process change be should be done if the level of turbidity in raw water decreased from 7 to 3 NTUs?", -->
            <!-- options: ["Increase Chemical Dosage", "Decrease Chemical Dosage", "Increase Chlorine Dosage", "Decrease Fluoride Dosage"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "When pumping from Well #1 the static level of Well #2 drops. What causes this?", -->
            <!-- options: ["Water Theft", "Drought Conditions", "Overlapping Fields of Influence", "Water Main Break"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "Operators working at a treatment plant should only use self contained breathing apparatus equipment that has been approved by what agency?", -->
            <!-- options: ["Occupational Safety and Health Administration (OSHA)", "Chemical Transportation Emergency Center (CTEC)", "National Institute of Occupational Safety and Health (NIOSH)", "Transportation Emergency Institute (TEI)"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What type of filtration is permitted under the Surface Water Treatment Rule?", -->
            <!-- options: ["140lbs Earth Filters", "Conventional, Direct, Slow Sand, and Diatomaceous Earth Filters", "Pressure Filters", "Carbon Filter s"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "Determining the pH is an important water quality test because the results indicate?", -->
            <!-- options: ["The balance between acidic and basic conditions", "The actual Temperature of the water", "How many filters can be added compared to disinfection residual", "The salinity of the water at that given time"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "In the ion exchange softening process, once the resin can no longer soften water it must?", -->
            <!-- options: ["Add more salt to softener", "Be regenerated", "Clean salt out of softener", "Be replaced immediately"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "With coagulation reactions when alum is used, the specific insoluble floc formed is a precipitate of?", -->
            <!-- options: ["Aluminum Hydroxide", "Sulumina", "Aluminum Sulfide", "Hydrochlide Aluminum"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "Solids contact basins have much shorter detention times than conventional treatment basins.", -->
            <!-- options: ["TRUE", "FALSE", "na", "na"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "The water purveyor must post the Consumer Confidence Report on a publicly accessible web site if it serves more than how many people?", -->
            <!-- options: ["1", "10000", "50000", "100000"], -->
                <!-- answer: 3 }, -->

<!-- 375 and up -->

        <!-- {question: "What adjustments will the operator of a surface water treatment plant have to make if the raw water is very high in turbidity levels?", -->
            <!-- options: ["Increase chemical feed pump", "Decrease chemical feed pump", "Use the Maximum Flocculator Paddle Speed Setting", "Use the Minimum Flocculator Paddle Speed Setting"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What are total dissolved minerals in rainwater typically close to?", -->
            <!-- options: ["10.00 mg/L", "48.00 mg/L", "40.00 mg/L", "1.00 mg/L"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What device collects the settled water as it leaves the sedimentation basin?", -->
            <!-- options: ["Effluent Flow Box", "Effluent Launder", "Effluent Weir", "Effluent Baffle"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "Powered activated carbon is usually used to control what?", -->
            <!-- options: ["Humic and Fulvic Acids", "Disinfectant by-products", "Organic Compounds Responsible for Tastes and Odors", "Synthetic Organic Compounds"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What should an operator do to compensate for temperature changes in a conventional water treatment plant with dual media filters that has very cold water in the winter and warm water in the summer?", -->
            <!-- options: ["Increase bed expansion in the winter compared to summer in order to remove turbidity", "Increase summer bed expansion and increase winter backwash flow rates", "Use more coagulants in the summer", "Sustain the same bed expansion without media loss by reducing or increasing backwash flow rate"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "When entering a permitted confined space entry structure, always complete a permit and?", -->
            <!-- options: ["Test the Air", "Ventilate", "And Have at Least 3 Persons on Stand-by", "All of the Above"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "How does Groundwater differ from Surface water sources?", -->
            <!-- options: ["Ground Water does not need chlorine treatment", "Ground Water is always clean and usually does not require disinfection", "Ground Water is colorless", "Ground Water has higher levels of hardness"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "What will ion exchange remove?", -->
            <!-- options: ["Hardness down to 7.4 mg/L as CaCO3", "Hardness down to 2.4 mg/L as CaCO3", "Hardness down to 9.3 mg/L as CaCO3", "All Hardness"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "What does total alkalinity refer to?", -->
            <!-- options: ["Total amount of carbonate, bicarbonate and hydroxide in solution", "The amount of alkaline in Cl2", "The amount of pH in raw water only", "None of the Above"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What is dental fluorosis?", -->
            <!-- options: ["Mottling of the Teeth", "Cavities", "Coating of Fluoride on the Teeth", "Flossing of the Teeth"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What effect will an increase in total dissolved solids in water to be treated be?", -->
            <!-- options: ["An increase in the time required for coagulation", "An increase in Methane", "A decrease in pH", "In increase in free chlorine residual"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What national law regulates underground disposal of wastes in deep wells?", -->
            <!-- options: ["The Toxic Substance Control Act", "The Safe Drinking Water Act", "The Comprehensive Environmental Response Compensation and Liability Act", "The Resource Conservation and Recovery Act"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "The upper surface of the zone of saturation of ground water in an unconfined aquifer is called the?", -->
            <!-- options: ["Capillary Fringe", "Spring", "Ground Water Table", "Evaporation"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "Manganese is rarely found in surface waters above a concentration of?", -->
            <!-- options: ["1.0 mg/L", "2.0 mg/L", "3.0 mg/L", "10.0 mg/L"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What would have the least impact on the efficiency of copper sulfate?", -->
            <!-- options: ["pH", "Alkalinity", "Water Hardness and Langlier Index", "Water Temperature"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What precipitates can foul a cation exchange resin?", -->
            <!-- options: ["Iron and Manganese", "Sulfates", "Chlorate and Borate", "Sodium Chloride and Potassium Chloride"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "Where is the least desirable point in a plug flow sedimentation basin for turbulent flow that resuspends solids would be in the?", -->
            <!-- options: ["Inlet Zone", "Outlet Zone", "Settling Zone", "Landing Zone"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "The advantage of using oxidant ozone is that it?", -->
            <!-- options: ["Pollution Free", "Is Inexpensive", "Little pH effect", "No Plant Operator Needed"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What is the most advantageous application point for powdered activated carbon?", -->
            <!-- options: ["After Coagulation", "In the Filters", "Raw Water Intake", "After Oxidation with Chlorine"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "Microorganisms that require dissolved or free oxygen are?", -->
            <!-- options: ["Aerobic", "Anaerobic", "Organic", "Inorganic"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What will neutralize chlorine?", -->
            <!-- options: ["Calcium Carbonate", "Chloramines", "Sodium Thiosulfate", "Ammonia Oxide"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "Permanganate reactions are highly dependent on?", -->
            <!-- options: ["Water Temperature", "Chlorine Residual", "pH", "Alum Level"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What will accurately measure 500mL solution?", -->
            <!-- options: ["Measuring Cup", "Beaker", "Anything larger than 500-mL", "500-mL Volumetric Flask"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "What percentage of the air is usually converted to ozone if air is used to generate ozone?", -->
            <!-- options: ["1 to 3%", "15-25%", "40-50%", "0.99"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "How many colonies per mI must the HPC test results show to be considered a reliable sample for coliform bacteria?", -->
            <!-- options: ["1", "100", "500", "8"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "Backwashing rate procedures should be reassessed to determine the cause of granular activated carbon loss if?", -->
            <!-- options: ["The loss per year is less than 2 inches", "The loss per year exceeds 0.02 inches", "The loss per year exceeds 1/2 inch", "The loss per year exceeds 2 inches"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "CTs are based on?", -->
            <!-- options: ["Concentration of CL2 and Time", "pH", "Temperature", "All of the above"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "What will cause reverse osmosis membranes to compact faster?", -->
            <!-- options: ["High Pressure", "Higher Iron Content", "Higher Chlorine Contact", "Higher pH"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "Why is it important to reduce turbidity?", -->
            <!-- options: ["To remove pathogens", "To remove color in the finished water", "To remove corrosion", "To remove taste and odor from water"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "The chlorine demand with vary with?", -->
            <!-- options: ["Population", "Local and State Laws", "Temperatures", "All of the above"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What type of charge do the compounds that form when iron or aluminum salts react with water have?", -->
            <!-- options: ["Negative", "Positive", "Neutral", "No Charge"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "Daily flow rates are limited in a conventional treatment plant due to the detention time needed to settle the floc and its sedimentation basin. What is the time range for the clarifier?", -->
            <!-- options: ["A Few Minutes", "2-4 hours", "A Few Seconds", "24 hours or more"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "Pathogenic organisms?", -->
            <!-- options: ["Effect Taste and Odor", "Cause Corrosion", "Disease causing organisms", "Harmless"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "Sludge should be removed from a gravity sedimentation basin when reaching a level of?", -->
            <!-- options: ["0.01", "0.02", "0.03", "0.04"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What type of polar bonds are between the hydrogen atoms and the oxygen atom in water?", -->
            <!-- options: ["van der Waals", "Ionic", "Hydrogen Bonding", "Covalent"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "Turbidity in the drinking water system can not exceed?", -->
            <!-- options: ["00.15 ntu", "3 ntu", "00.00001 ntu", "5 ntu"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "What is the most effective method for the removal of disinfection by products?", -->
            <!-- options: ["Reverse Osmosis", "Granular Activated Carbon", "Lime Softening", "Ultrafiltration"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "What is the best addition for water that is highly colored due to organic matter?", -->
            <!-- options: ["A small increase of nonionic polymer", "Increase of lime and the coagulant being used", "The addition of an acid to lower pH before coagulation", "The addition of lime"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What is the main problem if particle agglomeration is occurring in a filter for iron and manganese removal at the interface of the coal layer below?", -->
            <!-- options: ["Coal layer is too coarse", "Coal layer is too fine", "Oxidant is too weak", "Coagulant dosage is excessive"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "When doing coliform analysis use the presence-absence method, a sample should be incubated for?", -->
            <!-- options: ["12 and 14hrs at 76 degrees Celsius", "24 and 48hrs at 35 degrees Celsius", "5 and 8hrs at 22 degrees Celsius", "14 and 16hrs at 33 degrees Celsius"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "The fusible metal plugs on chlorine containers are designed to melt at what temperatures?", -->
            <!-- options: ["129-144 Degrees Fahrenheit", "158-165 Degrees Fahrenheit", "265-321 Degrees Fahrenheit", "350-400 Degrees Fahrenheit"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "The injection of fluoride should be as far away as possible from any chemical containing?", -->
            <!-- options: ["Calcium", "Aluminum from Alum", "Chlorine", "Soda Ash"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "OSHA stands for?", -->
            <!-- options: ["Occupational Safety and Administration", "Optional Safety and Health Administration", "Occupational Safety and Health Administration", "Occupational Safety and Healing Administration"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What tests are performed most frequently in drinking water systems?", -->
            <!-- options: ["Lead and Copper and Taste and Odor", "Hard Water and Soft Water", "Turbidity and Coliform Bacteria", "Chlorine Residual and Physical"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "After a backwash, to avoid turbidity spikes at the start of a service run, filters should be equipped with?", -->
            <!-- options: ["Filter-to-waste piping", "Waster Water Systems", "Sedimentation Basins", "Crane Operators"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What is the best probable solution if rotifers are visible in finished water?", -->
            <!-- options: ["Use oxygen deprivation", "Super chlorinate the water plant", "Use aeration followed by lime softening before the settling process", "Optimize coagulation, flocculation, and filtration"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "What advantage over Aluminum Sulfate does Ferric Sulfate have?", -->
            <!-- options: ["Cheaper to Use", "More Dense Floc", "Not Corrosive", "Less Dense Floc"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "A method of destabilization is reducing the zeta potential to allow floc formation. What would be an acceptable ZP range?", -->
            <!-- options: ["Less than -10", "Less than -22", "Greater than 10", "Greater than -10"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "Which is not considered to be a waterborne disease?", -->
            <!-- options: ["Giardia lamblia", "Cryptosporidium Parvum", "Legionella Pneumophila", "Mumps Virus"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "Low temperature water can be compensated for when using Alum by?", -->
            <!-- options: ["Raising the pH Level in the water", "Let water warm up in the settling pond", "Increasing the Alum dosage", "Lowering the Alum dosage"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "If a rapid gravity filter is well operated, the finished water will have?", -->
            <!-- options: ["Finished Ammonia", "Cl2", "Less than 0.1 NTUs", "Ideal clarity"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "The scattering of light by the particles in finished water is from the turbidity caused by", -->
            <!-- options: ["Silt and Clay", "Inorganics", "Salt and Pepper", "Blue Stone"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What would be the short term goal when a water source is destroyed or damaged by some type of disaster that causes total contamination?", -->
            <!-- options: ["Install a dual potable-nonpotable water system", "Draw water from an adjoining system or systems", "Construct a new raw water source", "Clean up contamination caused by the disaster"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "What is measured to determine total alkalinity?", -->
            <!-- options: ["pH of water", "Amount of acid required to change the pH into the 3.7-4.8 range", "Cl2 Residual", "Carbon Count"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "Records of sanitary surveys must be kept for?", -->
            <!-- options: ["3 years", "5 years", "10 years", "Forever"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "If the water temperature decreases this will cause the disinfection action of chlorine to?", -->
            <!-- options: ["Increase", "Decrease", "Stay the Same", "Inactivate"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "What type of water violation requires an all clear notification be given to the public?", -->
            <!-- options: ["Tier I", "Tier II", "Tier III", "Tier IV"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "When a raw water analysis shows the presence of anabaena, ceratium and oscillatoria, what problem may arise?", -->
            <!-- options: ["Low pH", "THMs", "Reduced CT", "Customer Complaints Regarding Tastes and Odors"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "The temperature range at which coliform bacteria samples must be stored before being delivered to a lab is?", -->
            <!-- options: ["4-10 degrees Fahrenheit", "12-22 degrees Fahrenheit", "12-88 degrees Celsius", "4-10 degrees Celsius"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "If iron bacteria is causing corrosion problems in the filters, what is the best solution?", -->
            <!-- options: ["Optimize the settling process", "Add lime at 50 mg/L to one filter at a time", "Protect metal parts of the filter by adding zinc", "Superchlorinate"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "What should the flexible copper tubing be rated at the connects a 150lb chlorine cylinder to a manifold?", -->
            <!-- options: ["25 psi", "100 psi", "250 psi", "500 psi"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What oxidant should be fed as early as possible in the treatment process to allow for complete reaction before it enters the distribution system?", -->
            <!-- options: ["Chlorine Dioxide", "Ozone", "Potassium Permanganate", "Chloramines"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "At minimum, the Surface Water Treatment Rule requires surface water users to use what two treatment methods?", -->
            <!-- options: ["Filtration and Disinfection", "Ozone and UV", "Chlorine and Chloramines", "Sedimentation and Coagulation"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What could be the reason for reduced pump flow, deteriorating pump impellers, plugging Needle Valves, and clogging PRV and Surge Control Valves?", -->
            <!-- options: ["Change in Water Temperature", "Sand or other material from the aquifer entering the well pump", "Backflow", "Broken Foot Valve"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "Past the breakpoint chlorination point, what percentage of the total chlorine residual should be free chlorine?", -->
            <!-- options: ["10-15%", "50-75%", "85 to 90%", "0.99"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What chemical is slacked lime?", -->
            <!-- options: ["Ca(HCO3)2", "Ca(OH)2", "Ca(H2O)2", "CaCO3"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "What occurs in raw water as the level of ammonia decreases?", -->
            <!-- options: ["Nothing Measurable", "THMs fall to 0", "The DPD will turn red", "Chloramines will form before the breakpoint and less Cl2 will be needed to reach breakpoint"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "What is the primary drawback for facilities that use ultra violet light to disinfect water?", -->
            <!-- options: ["It causes a high electric bill", "Consumers complain due to the odd light from the facility", "Operators break out in a dance party at night", "There is potential for the light bulbs to be coated with material that may obscure the light like dust."], -->
                <!-- answer: 3 }, -->
        <!-- {question: "What are the chemical symbols for hypochlorous acid and hypochlorite ions?", -->
            <!-- options: ["HOCI & OCI-", "H20 & HCI", "HCI & HOCI", "HOCI & OCI-"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "What is the filtration flow rate through a manganese greensand pressure filter at 10 degrees Celsius?", -->
            <!-- options: ["1 to 2 gpm/ft2", "2 to 3 gpm/ft2", "4 to 5 gpm/ft2", "9 to 12 gpm/ft2"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "A pro of chloramines is?", -->
            <!-- options: ["Long lasting residual that will reach farther in the water system", "Keeps water in lower temperature", "Has a really low pH", "Prevents algae from clogging the filters"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "A water molecule is made up of ?", -->
            <!-- options: ["One Hydrogen Atom and Two Oxygen", "One Hydrogen Atom and One Oxygen", "Two Hydrogen Atoms and One Oxygen", "Two Hydrogen Atoms and Two Oxygen"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "For lime-soda ash softening plants, what is the most economical sludge disposal method?", -->
            <!-- options: ["Sand Drying Beds", "Disposal into the Sewage System", "Landfill the Sludge", "Lagoons"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "The minimum detention time in a conventional detention basin is?", -->
            <!-- options: ["1-5 mins", "10-15 mins", "1-2hrs", "4 Hours"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "The cl2 residual in water may be determined by using the reagent?", -->
            <!-- options: ["Kryptonite", "Boron", "DPD - Diethyl-p-phenylenediamine", "Carbonate"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "A coliform sample is considered invalid and a new sample must be taken within 24hrs if the HPC count is above?", -->
            <!-- options: ["1 CFU", "100 CFU", "500 CFU", "10 CFU"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What can immediately occur if newly installed manganese greensand was not skimmed of the fines after backwashing and stratification steps were completed?", -->
            <!-- options: ["Mudball Formation", "Shorter Filter Runs", "Cracks Would Develop in the Bed", "Uneven Flow Through the Bed"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "What is the most important reason to reduce turbidity?", -->
            <!-- options: ["Clogs Bar Screens", "Clogs Transducer Sensors", "To Remove Pathogens", "Causes Incorrect Meter Readings"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "When abundant in water, what algae genera are most likely to cause taste and odor issues when abundant in water?", -->
            <!-- options: ["Spirogyra", "Volvox", "Chlorella", "Oocysts"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "Chlorine is chosen over chloramines because chlorine?", -->
            <!-- options: ["Is a much stronger oxidant", "Has a longer lasting residual", "Comes in tablet form", "Does not cause THMs"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "HPC and Coliform tests are the same because they both?", -->
            <!-- options: ["Must be frozen within 8hrs", "Have a volume of 100mL and the initial incubation period is 24hrs at 35 degrees Celsius", "Must be taken after the water in the system has been motionless for 12hrs", "All of the above"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "In a permit entry confined space, who is responsible for terminating entries?", -->
            <!-- options: ["Entry Supervisor", "State or Local Official", "Person Who Enters the Confined Space", "USEPA"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What would be the most probable solution to control algae in the source water if the algae is clogging the filters in the water plant?", -->
            <!-- options: ["Control Nutrients", "Backwash Filters More Frequently", "Decrease Oxygen Levels", "Use Activated Carbons"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What is the natural attraction between particles that can be used to collect them into larger groups once destabilization has occurred?", -->
            <!-- options: ["van der Waal's force", "Zeta Potential", "Electronzoning", "Flux Capacitating"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "A connection between a potable water system and a non potable water system is?", -->
            <!-- options: ["An Auxiliary Water Source", "A Cross-Connection", "Permitted for Fire Flow", "Allowed During Drought Years"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "During filtration, what role does the action of straining of suspended particles play?", -->
            <!-- options: ["Minor", "Major", "Good", "Fair"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "A common chemical added to boost alkalinity is?", -->
            <!-- options: ["Calcium Hydroxide", "Alum", "Copper Sulfate", "Nitrites"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "Which would be an indication that there is an issue with a part of the coagulation-flash mix-flocculation process operation?", -->
            <!-- options: ["TDS Meter Reads 0 NTU", "Sedimentation Basin Showing Various Rainbow like Colors", "Slight Settling of Floc Particles in the Slow Mix Basin", "Pin Floc Formed in Low Turbidity Water"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What is the sample size for lead and copper analysis?", -->
            <!-- options: ["1 mL", "100 mL", "1,000 mL", "10,000 mL"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What type of chlorine gas feeding equipment would be most appropriate for distribution systems where re-chlorination is required?", -->
            <!-- options: ["Chlorinator", "Stabilizer", "Venturi", "Compound-loop control gas feeder"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "Opening the discharge valve one full turn on a chlorine cylinder will?", -->
            <!-- options: ["Permit Half Discharge", "Permit 1/4 Discharge", "Permit Maximum Discharge", "Permit Minimum Discharge"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What is the most effective disinfection residual?", -->
            <!-- options: ["Chloride (NaCl)", "Sulfur (S)", "Alum (Al)", "Hypochlorous Acid (HCLO)"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "An artesian spring occurs when", -->
            <!-- options: ["the water has too many taste and odors to be used for consumption", "there are too many natural nutrients in water to be filtered", "water flows down a hill from gravity", "Groundwater has enough pressure to rise above an upper confining layer"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "In which state are Giardia most vulnerable to inactivation through disinfection?", -->
            <!-- options: ["Trophozoite", "Cyst", "Dormant", "Crypto"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "Potassium permanganate and manganese greensand are sometimes used to?", -->
            <!-- options: ["Increase the pH of raw water", "Coat pipes with film to prevent corrosion", "Never used together", "Keep Iron Soluble in Water"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "A property that is important to water treatment that is physical as opposed to chemical is?", -->
            <!-- options: ["pH", "Turbidity", "Dissolved Solids", "Electrical Conductivity"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "What is the optimal pH range for the removal of particulate matter when using Alum as a coagulant?", -->
            <!-- options: ["6.5-7.2", "5.5-6.0", "8.3-9.1", "3.4-4.3"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "Trihalomethanes (THM's) are primarily a concern in?", -->
            <!-- options: ["Hard Water", "Water before chlorine disinfection treatment", "Water after chlorine disinfection treatment", "Lakes and Reservoirs"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "The proper emergency kit for a TON chlorine cylinder is?", -->
            <!-- options: ["Kit A", "Kit B", "Kit C", "Kit from Knight Rider"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "In a thermally stratified reservoir, water located beneath the thermocline may?", -->
            <!-- options: ["Contain tastes and odors due to H2S formation", "Contain high levels of Cl2", "Contain increased levels of T-10000", "Contain no DO"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "What is the usual effective pH range of iron salt coagulants?", -->
            <!-- options: ["0-1", "1.5-2.3", "3.5 to 9.5", "4.8-9.3"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "The process of the build up of corrosion products is known as?", -->
            <!-- options: ["Tuberculation", "Physiochemical Deposition", "Electrochemical Deposition", "Deposition"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "The proper emergency kit for a 150lb chlorine cylinder is?", -->
            <!-- options: ["Kit A", "Kit B", "Kit C", "Kit from Knight Rider"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "Protozoa that must be removed from raw water are?", -->
            <!-- options: ["Klebsiella and Citribacter", "Hepatitis and H1N1", "Giardia and Cryptosporidium", "Total Dissolved Solids"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "A public water system that can not meet the required removal of TOC can comply if the source water TOC level is what, calculated quarterly as a running annual average.", -->
            <!-- options: ["<1.0 mg/L", "<1.2 mg/L", "<2.0 mg/L", "<2.8 mg/L"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "Who can declare the vulnerability of a water source?", -->
            <!-- options: ["A contractor or a consultant", "The State", "The Water Purveyor", "All of the above"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "Pure water can be found?", -->
            <!-- options: ["Surface Water", "Ground Water", "Sterilized Water Mains", "In a laboratory"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "What conditions will +Eh values of water support?", -->
            <!-- options: ["Low pH Values", "Organic Acid Production", "Aerobic Activities", "Anaerobic Activities"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What gasket is the best to use when connecting a chlorine cylinder or container to the chlorine feed system?", -->
            <!-- options: ["Rubber Gasket", "Fiber Gasket", "Lead Gasket", "The original gasket must not be replaced"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What type of sedimentation basins have the flow of water admitted at an angle?", -->
            <!-- options: ["Spiral Flow Basins", "Center Feed Settling Basins", "Square Settling Basins", "Rectangular Settling Basins"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "In the MNO-MUG test the presence of E.coli is indicted by?", -->
            <!-- options: ["Red or Pink Color", "Blue Fluorescence", "Meter Count", "Green Color"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "What is put in place in a reservoir to create an even flow rate through the entire volume of a clearwell to provide a consistent amount of detention time and minimize short-circuiting?", -->
            <!-- options: ["Wear Rings", "Baffles", "Filters", "Sedimentation Basin"], -->
                <!-- answer: 1 }, -->
        <!-- {question: "What unit process will diatoms most likely replace?", -->
            <!-- options: ["Rumination", "Sedimentation", "Dalton", "Filtration"], -->
                <!-- answer: 3 }, -->
        <!-- {question: "The Surface Water Treatment Rule states that multibarrier treatment must result in the inactivation of Giardia cysts and viruses by?", -->
            <!-- options: ["4.0 log for viruses and 3.0 log for cysts", "1.0 log for viruses and 1.0 log for cysts", "4.0 log for viruses and 4.0 log for cysts", "3.0 log for viruses and 4.0 log for cysts"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "Test results from a multiple tube fermentation test for coliform bacteria are expressed as MPN (most probable number) per 100 milliliters, the number is determined from?", -->
            <!-- options: ["The number of positive presumptive tubes", "The difference between positive and negative tubes", "The number of positive confirmed tubes", "None of the above"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What is the rule that sets MCL's for harmful chemicals?", -->
            <!-- options: ["Disinfection By Product Rule", "Safe Drinking Water Act", "Surface Treatment Water Rule", "O'doyle Rules"], -->
                <!-- answer: 0 }, -->
        <!-- {question: "If there is a notification of a HazMat spill of an unknown chemical into a stream that provides water to a water treatment plant, what would be the best action taken?", -->
            <!-- options: ["Shutdown the water plant", "Add more Cl2", "Temporary close the raw water inlet from that stream and use only well water to meet the demand", "Lower the pH of the raw water"], -->
                <!-- answer: 2 }, -->
        <!-- {question: "What should an authorized entrant do before he/she enters a permitted confined space?", -->
            <!-- options: ["Verify the availability of rescue services", "Put on SCUBA gear", "Verify the internal atmosphere of the space is tested to measure oxygen content, presence of flammable gasses, and vapors, and potentially toxic air contaminants", "None of the above"], -->
                <!-- answer: 2 }, -->








    ];

    let currentQuestions = [];

    function shuffleArray(array) {
      return array.map(value => ({ value, sort: Math.random() }))
                  .sort((a, b) => a.sort - b.sort)
                  .map(({ value }) => value);
    }

    function shuffleQuestions() {
      currentQuestions = questions.map(q => {
        const originalAnswerText = q.options[q.answer];
        const shuffledOptions = shuffleArray(q.options);
        const newAnswerIndex = shuffledOptions.indexOf(originalAnswerText);
        return {
          question: q.question,
          options: shuffledOptions,
          answer: newAnswerIndex
        };
      }).sort(() => Math.random() - 0.5);

      displayQuestions();
    }

    function displayQuestions() {
      const container = document.getElementById("quiz-container");
      container.innerHTML = "";

      currentQuestions.forEach((q, qIndex) => {
        const qDiv = document.createElement("div");
        qDiv.className = "question";

        const qTitle = document.createElement("h3");
        qTitle.textContent = `Q${qIndex + 1}: ${q.question}`;
        qDiv.appendChild(qTitle);

        q.options.forEach((opt, optIndex) => {
          const label = document.createElement("label");
          label.innerHTML = `
            <input type="radio" name="q${qIndex}" value="${optIndex}">
            ${opt}
          `;
          qDiv.appendChild(label);
          qDiv.appendChild(document.createElement("br"));
        });

        const actionRow = document.createElement("div");
        actionRow.className = "action-row";

        const submitBtn = document.createElement("button");
        submitBtn.textContent = "Submit Answer";
        submitBtn.onclick = () => checkAnswer(qIndex);
        actionRow.appendChild(submitBtn);

        const feedback = document.createElement("div");
        feedback.id = `feedback${qIndex}`;
        feedback.className = "feedback";
        actionRow.appendChild(feedback);

        qDiv.appendChild(actionRow);
        container.appendChild(qDiv);
      });
    }

    function checkAnswer(qIndex) {
      const radios = document.getElementsByName(`q${qIndex}`);
      let selectedIndex = -1;
      for (let i = 0; i < radios.length; i++) {
        if (radios[i].checked) {
          selectedIndex = parseInt(radios[i].value);
          break;
        }
      }

      const feedback = document.getElementById(`feedback${qIndex}`);
      if (selectedIndex === -1) {
        feedback.textContent = "⚠️ Please select an answer.";
        feedback.className = "feedback incorrect";
        return;
      }

      const correctIndex = currentQuestions[qIndex].answer;
      if (selectedIndex === correctIndex) {
        feedback.textContent = "✅ Correct!";
        feedback.className = "feedback correct";
      } else {
        const correctAnswer = currentQuestions[qIndex].options[correctIndex];
        feedback.textContent = `❌ Incorrect. Correct answer - - - ${correctAnswer}`;
        feedback.className = "feedback incorrect";
      }

      radios.forEach(r => r.disabled = true);
    }

    // Shuffle and render on page load
    window.onload = shuffleQuestions;
  </script>
</body>
</html>
