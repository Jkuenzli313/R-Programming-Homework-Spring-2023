data(iris)
head(iris)

# first create species list
sp_ids <- unique(iris$Species)

# setup output matrix to capture some values
trait_average <- matrix(NA, nrow=length(sp_ids), ncol=ncol(iris)-1)
rownames(num_samples) <- sp_ids
colnames(trait_sum) <- names(iris[ , -ncol(iris)])

# loop through the 3 species
for(i in seq_along(sp_ids)) {
  
  # subset data down to specific species, drop species column
  iris_sp <- subset(iris, subset=Species == sp_ids[i], select=-Species)
  
  # loop through columns 1-4 (j) and rows 1-50 (k); sum of columns 1 through 4 and then number of rows in that column
  for(j in 1:(ncol(iris_sp))) {
    t <- 0
    y <- 0
    if (nrow(iris_sp) > 0) {
      for(k in 1:nrow(iris_sp)) {
        x <- x + iris_sp[k, j]
        y <- y + 1
      }
      output[i, j] <- x / y 
    }
  }
}
output

# renaming variables
# setup output matrix to capture some values/shorten lines of code
trait_average <- matrix(NA, nrow=length(sp_ids), ncol=ncol(iris)-1)
rownames(trait_average) <- sp_ids
colnames(trait_average) <- names(iris[ , -ncol(iris)])
for(i in seq_along(sp_ids)) {
  iris_sp <- subset(iris, subset=Species == sp_ids[i], select=-Species)
  
  for(j in 1:(ncol(iris_sp))) {
    trait_sum <- 0
     num_samples <- 0
    for(k in 1:nrow(iris_sp)) {
      trait_sum <- trait_sum + iris_sp[k, j]
      num_samples <- num_samples + 1
    }
    trait_average[i, j] <- trait_sum / num_samples 
  }
}
trait_average

colnames(trait_average) <- names(iris[ , -ncol(iris)])

mean(nrow(iris_sp))

# sum of a sequence

x <- (1:10)

y <- cumsum(x)


for (val in cumsum(x)) {
  if (val > 10) {
    print('N/A')
  }
}
cumsum(x)
x <- (1:10)

y <- cumsum(x)    


y [y > 10] <- "N/A"




  
  