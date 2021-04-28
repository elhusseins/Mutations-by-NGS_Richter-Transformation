# Mutations-by-NGS_Richter-Transformation
Mutations by NGS_Richter Transformation


#patients by rows
p1 <- c(0,0,0,0,1,0,1,0,0,0,0,0,0,0,0,0)
p2 <- c(0,0,0,0,0,0,0,1,0,0,0,0,0,0,0,0)
p3 <- c(0,0,0,1,1,0,0,0,1,0,0,0,0,0,0,0)
p4 <- c(1,1,0,0,1,0,0,0,0,1,0,0,0,0,0,0)
p5 <- c(1,1,0,1,0,0,0,0,0,0,0,0,0,0,0,0)
p6 <- c(0,0,0,0,1,0,0,0,0,0,0,0,0,0,0,0)
p7 <- c(0,0,1,0,1,0,0,0,0,1,0,0,0,0,0,0)
p8 <- c(0,0,1,0,1,0,0,0,0,0,0,0,0,0,0,0)
p9 <- c(0,0,1,0,1,0,0,0,0,0,1,1,0,0,0,0)
p10 <- c(1,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0)
p11 <- c(0,0,0,0,0,0,0,0,1,0,0,0,0,0,0,0)
p12 <- c(0,0,0,0,0,0,0,0,0,0,0,0,1,1,1,0)
p13 <- c(0,0,1,0,1,0,0,0,0,0,0,0,0,0,0,1)
p14 <- c(0,0,0,0,1,0,0,0,0,0,0,0,0,0,0,0)

#matrix
patients <- cbind(p1, p2, p3, p4, p5, p6, p7, p8, p9, p10, p11, p12, p13,p14)
patients
data <- matrix(patients, byrow = TRUE, nrow = 14, ncol = 16)

#col & rownames
colnames(data) <- c('ATM','BTK','NOTCH1','SF3B1','TP53','FBXW7','SPEN','DDX3X','FAT1','BIRC3','CALR','ZYMYM3','CD79b','CXCR4','MYD88','POT1')
rownames(data) <- c(1:14)

#mutation_table
data

#dataframe
as.data.frame(data)

# final with dendro
heatmap(data, xlab = 'genes', ylab = 'patients', labRow = NA, keep.dendro = TRUE, main = 'Mutation by Next Generation Sequencing', margins = c(5, 5))

#final witout dendro
heatmap(data, xlab = 'genes', ylab = 'patients', labRow = NA, Rowv = NULL, Colv = NULL, main = 'Mutation by Next Generation Sequencing', margins = c(5, 5))

