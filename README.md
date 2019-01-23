# DoFrenchStudentsCostTooMuch?"

Project by Gloriana Lang, India Hayler Kerle, Francesco Lanzone, Maximilian Gahntz, and Stephanie Tran. 

January 2019 Sciences Po Datathon💻

# Introduction

## OPENING REGION FILE AND SUMMARIZING NUMBER OF STUDENTS
eduregio <- read_delim("./Enrollment.csv", delim = ";", locale = locale(encoding = "Latin1"))

studnum <- eduregio %>% 
  group_by(Région) %>%
  summarise(studnum = sum(as.numeric(`Effectifs d'étudiants inscrits 2014-15`), na.rm = TRUE))

## importing expenses
eduexp <- read_delim("./SpendingData.csv", delim = ";", locale = locale(encoding = "Latin1"))

studnum <- studnum[-c(5, 7),]
studnum <- studnum[-c(7, 8, 11, 12),]
eduexp <- eduexp[-c(14:70),]
