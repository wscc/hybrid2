# hybrid2

    This is the R code for modification of WGCNA, combining the features of signed and unsigned WGCNA.
    hpickSoftThreshold.r for picking the power, hadjacency.r for calculating the adjacency from expression matrix.
    you can use it as below:
    
    library(WGCNA)
    library(doParallel)
    options(stringsAsFactors = F)

    source('hpickSoftThreshold.r')
    enableWGCNAThreads()
    powers = c(seq(1,9,by=1),seq(10,30,by=2))
    sft<-hpickSoftThreshold(t(Expr),powerVector = powers, networkType = "hybrid2", corFnc = , verbose = 5)


    source('Hadjacency.r')
    adj<-Hadjacency(datExpr=Expr,type='hybrid2',power= ,corFnc= )
    TOM<-TOMsimilarity(adj, TOMType = , verbose = 1)


    # after TOM matrix done, you can do any thing on it by functions in original WGCNA package.
