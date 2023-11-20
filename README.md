# Data
df <- data.frame(
  Population = c("Spring", "Spring", "Swamp", "Swamp"),
  Clarity = c("Clear", "Tea", "Clear", "Tea"),
  Mean = c(0.106, 0.08, 0.108, 0.078),
  SE = c(0.006, 0.005, 0.007, 0.005)
)

library(ggplot2)

ggplot(df, aes(x = Population, y = Mean, fill = Clarity)) +
  geom_boxplot(position = position_dodge(width = 0.8), width = 0.7) +
  geom_point(position = position_dodge(width = 0.8), size = 3, shape = 21, color = "black", fill = "white") +
  geom_errorbar(aes(ymin = Mean - SE, ymax = Mean + SE), position = position_dodge(width = 0.8), width = 0.25) +
  labs(title = "Boxplot by Population and Clarity",
       x = "Population",
       y = "Mean") +
  scale_fill_manual(values = c("Clear" = "skyblue", "Tea" = "lightgreen"))
