# Time-Series-Harmonic-Analysis-Swindon

This workflow uses GEE

    Copy the “sinosoidal function” into GEE.
    1. Define your study area as “study_area” and select a single point called “single_pixel”
    2. Edit “start_time” and “end_time” to your dates
    3. Edit “year_of_first_break” to one year after the start date (such that if your “start_time” is 1989-01-01, “year_of_first_break” would equal 1990)
    4. Edit the final number in “years” to equal the total number of years the study will use to create the sinosoidal function
    5. In the FOR loop, set statement 2 (“i<_”) to the total number of years in the study minus 1.
    6. Run the script
    7. Two images are exported (find above): "change_image" and "no_change_image"
    
    
    
    In a new script open “change_detection”
    8. Import from google drive the change layer and name it “change_image”
    9. Import from google drive the no-change layer and name it “no_change_image”
    10. Edit statement 1 to the minimum threshold value you wish to test multiplied by 100 (such if you wish to use a threshold of 0.98, use 98)
    11. Edit statement 2 to the maximum threshold value you wish to test, as before
    12. Edit “change_start” to the year you would like change detection to commence (e.g. 2003)
    13. Edit “change_end” to the final year you wish to detect change for (e.g. 2011 detects change up to 31st of December 2011)
    14. Run the script
    N.B. The number of images exported will depend on the number of threshold iterations desired.  Dates used in the paper are found as comments within this code file. 
    15. These layers are exported to google drive 
    N.B. Images of varying thresholds tested to find the most appropreate threshold are found in the folder "threshold".  The "validation image" uses a threshold of 0.93 and was the image used to compare with the PCC of LCM 2007 and 2015 ("PC_change_detection_reclassified" where 1 = change).  "time_of_change" uses a threshold of 0.93 and was used to test the accuracy of the models dating capability.
    
    
    In a new script open “classification”
    16. Upload and import your ground truth data (this is automatically named “table”), consisting of a classification and x, y points.  This uses Set C.
    17. Import your image you wish to classify (this is automatically named “image”)
    18. Define your study area (this is automatically named “geometry”)
    19. Run the script
    20. Image is exported to google drive
    N.B. This results in "classified_image".  
    
    
    To count cloud proportion:
    1. Open counting clouds
    2. Define your area of interest
    3. Define your start time and end time
    4. Run script, image is exported to google drive
    N.B. This results in "number_of_clouds"
