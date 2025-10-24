data2018 <- read.csv("samadult.csv")
library("dplyr")
datoslimpios <- select(data2018, AGE_P, MRACBPI2, BMI, 
                           CNKIND20, CANAGE20, 
                           PSAHAD, SMKEV, SMKREG,
                           SMKNOW, SMKSTAT2,
                           SMKQTY, CIGSDA1, DIBEV1, DIBAGE1,
                           DIFAGE2, HYPEV, ALDURA9, ALCHRC9,
                           ALDURA18, ALCHRC18)
datoslimpios$BMI <- data2018$BMI / 100
df_limpio <- datoslimpios[ !is.na(datoslimpios$CNKIND20),]

continuas <- select(df_limpio, AGE_P, BMI, 
                    CANAGE20, 
                    SMKREG,
                    SMKQTY, CIGSDA1,DIBAGE1,
                    DIFAGE2, ALDURA9,
                    ALDURA18)
continuas[is.na(continuas)] <- 0
boxplot(continuas)

S <- cov(continuas)
correlaciones <- cor(continuas)

corrplot::corrplot(correlaciones, method="color", type="upper", order="hclust",
                   addCoef.col = "black", diag=FALSE, number.cex = 0.5,
                   #Text label color and rotation
                   tl.col="black", tl.srt=45, family="Ubuntu Condensed", 
                   # Combine with significance
                   sig.level = 0.01, insig = "blank")
