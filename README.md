# hybrid2

    This is the R code for modification of WGCNA, combined the features of signed and unsigned WGCNA.
    hpickSoftThreshold.r for picking the power, hadjacency.r for calculating the adjacency from expression matrix.
    you can use it like:

    source('hpickSoftThreshold.r')
    enableWGCNAThreads()
    powers = c(seq(1,9,by=1),seq(10,30,by=2))
    sft<-hpickSoftThreshold(t(Expr),powerVector = powers, corFnc = bicor, networkType = "hybrid2", verbose = 5)


    source('Hadjacency.r')
    adj<-Hadjacency(datExpr=Expr,type='hybrid2',power=12,corFnc='bicor')
    TOM<-TOMsimilarity(adj, TOMType = "signed", verbose = 1)
