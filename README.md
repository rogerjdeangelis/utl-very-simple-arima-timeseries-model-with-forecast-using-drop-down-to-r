# utl-very-simple-arima-timeseries-model-with-forecast-using-drop-down-to-r
Very simple arima timeseries model with forecast using drop down to r.
    Very simple arima timeseries model with forecast using drop down to r                                                 
                                                                                                                          
    R have excellect time series functionality                                                                            
                                                                                                                          
    Given a list of gpas by month for 4 years predict the next 6 month                                                    
                                                                                                                          
    90 percent of the R code is needed just to input and output to SAS.                                                   
    Only two lines of code for the model. R is complex list happy.                                                        
                                                                                                                          
    github                                                                                                                
    https://tinyurl.com/y6dt92bb                                                                                          
    https://github.com/rogerjdeangelis/utl-very-simple-arima-timeseries-model-with-forecast-using-drop-down-to-r          
                                                                                                                          
    SAS forum                                                                                                             
    https://tinyurl.com/y5yb59jv                                                                                          
    https://communities.sas.com/t5/SAS-Programming/using-SAS-for-forecasting/m-p/542731                                   
                                                                                                                          
    options validvarname=upcase;                                                                                          
    libname sd1 "d:/sd1";                                                                                                 
    data sd1.have;                                                                                                        
      input x @@;                                                                                                         
      seq=_n_;                                                                                                            
    cards4;                                                                                                               
    2.4 2.4 2.4 2.2 2.1 1.5 2.3 2.3 2.5 2 1.9 1.7 2.2 1.8 3.2 3.2 2.7                                                     
    2.2 2.2 1.9 1.9 1.8 2.7 3 2.3 2 2 2.9 2.9 2.7 2.7 2.3 2.6 2.4 1.8                                                     
    1.7 1.5 1.4 2.1 3.3 3.5 3.5 3.1 2.6 2.1 3.4 3 2.9                                                                     
    ;;;;                                                                                                                  
    run;quit;                                                                                                             
                                                                                                                          
                                                                                                                          
        3  6  9  12 15 18 21 24 27 30 33 36 39 42 45 48                                                                   
      X +--+--+--+--+--+--+--+--+--+--+--+--+--+--+---+                                                                   
    3.5 +                                             + 3.5                                                               
    3.4 +      ____ ____   _                          + 3.4                                                               
    3.3 +     / ___|  _ \ / \   Grade Point Average   + 3.3                                                               
    3.2 +    | |  _| |_) / _ \ before grade inflation + 3.2                                                               
    3.1 +    | |_| |  __/ ___ \                     + + 3.1                                                               
    3.0 +     \____|_| /_/   \_\                    | + 3.0                                                               
    2.9 +                                           | + 2.9                                                               
    2.8 +                                           | + 2.8                                                               
    2.7 +                                           | + 2.7                                                               
    2.6 +                          +                | + 2.6                                                               
    2.5 +                         / \               + + 2.5                                                               
    2.4 + ------+                /   +             /  + 2.4                                                               
    2.3 +        \           +--+    |            /   + 2.3                                                               
    2.2 +         \          |       |          +/    + 2.2                                                               
    2.1 +          +--+      |       |         /      + 2.1                                                               
    2.0 +              \     +       +        /       + 2.0                                                               
    1.9 +               \   /         \--+   /        + 1.9                                                               
    1.8 +                \ /              \ /         + 1.8                                                               
    1.7 +                 +                +          + 1.7                                                               
    1.6 +                                             + 1.6                                                               
    1.5 +                                             + 1.5                                                               
    1.4 +                                             + 1.4                                                               
        |                                             |                                                                   
        +--+--+--+--+--+--+--+--+--+--+--+--+--+--+---+                                                                   
        3  6  9  12 15 18 21 24 27 30 33 36 39 42 45 48                                                                   
                                      __  __                                                                              
                _ __ ___   ___  _ __ | |_| |__                                                                            
               | '_ ` _ \ / _ \| '_ \| __| '_ \                                                                           
               | | | | | | (_) | | | | |_| | | |                                                                          
               |_| |_| |_|\___/|_| |_|\__|_| |_|                                                                          
                                                                                                                          
    *            _               _                                                                                        
      ___  _   _| |_ _ __  _   _| |_                                                                                      
     / _ \| | | | __| '_ \| | | | __|                                                                                     
    | (_) | |_| | |_| |_) | |_| | |_                                                                                      
     \___/ \__,_|\__| .__/ \__,_|\__|                                                                                     
                    |_|                                                                                                   
    ;                                                                                                                     
                                                                                                                          
    Output SAS datasets                                                                                                   
                                                                                                                          
                 Member                                                                                                   
    #  Name      Type                                                                                                     
                                                                                                                          
    1  FORECST   DATA                                                                                                     
    2  COEF      DATA                                                                                                     
    3  VARCOEF   DATA                                                                                                     
    4  SIGMA2    DATA                                                                                                     
    5  LOGLIK    DATA                                                                                                     
    6  AIC       DATA                                                                                                     
    7  ARMA      DATA                                                                                                     
    8  RESIDUAL  DATA                                                                                                     
                                                                                                                          
    Six Month predictions                                                                                                 
                                                                                                                          
    WORK.FORECST total obs=6                                                                                              
                                                                                                                          
    Obs    FORCST_P    FORCST_SE                                                                                          
                                                                                                                          
     1      3.03376     0.57066                                                                                           
     2      3.07414     0.60442                                                                                           
     3      3.11453     0.64204                                                                                           
     4      3.15492     0.68333                                                                                           
     5      3.19530     0.72808                                                                                           
     6      3.23569     0.77607                                                                                           
                                                                                                                          
                                                                                                                          
        3  6  9  12 15 18 21 24 27 30 33 36 39 42 45 4   48 51 54                                                         
      X +--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+////--+--+--+                                                       
    3.5 +                                             |           + 3.5                                                   
    3.4 +     ____ ____   _                           |Prediction + 3.4                                                   
    3.3 +    / ___|  _ \ / \                          |---------- + 3.3                                                   
    3.2 +   | |  _| |_) / _ \                         |     +--+  + 3.2   |                                               
    3.1 +   | |_| |  __/ ___ \                        |    /      + 3.1   |                                               
    3.0 +    \____|_| /_/   \_\                     +-|  -+       + 3.0                                                   
    2.9 +                                           | |           + 2.9                                                   
    2.8 +                                           | |           + 2.8                                                   
    2.7 +                                           | |           + 2.7                                                   
    2.6 +                          +                | |           + 2.6                                                   
    2.5 +                         / \               + |           + 2.5                                                   
    2.4 + ------+                /   +             /  |           + 2.4                                                   
    2.3 +        \           +--+    |            /   |           + 2.3                                                   
    2.2 +         \          |       |          +/    |           + 2.2                                                   
    2.1 +          +--+      |       |         /      |           + 2.1                                                   
    2.0 +              \     +       +        /       |           + 2.0                                                   
    1.9 +               \   /         \--+   /        |           + 1.9                                                   
    1.8 +                \ /              \ /         |           + 1.8                                                   
    1.7 +                 +                +          |           + 1.7                                                   
    1.6 +                                             |           + 1.6                                                   
    1.5 +                                             |           + 1.5                                                   
    1.4 +                                             |           + 1.4                                                   
        |                                             |           |                                                       
        +--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+////--+--+--+                                                       
        3  6  9  12 15 18 21 24 27 30 33 36 39 42 45 48  48 51 54                                                         
                                          __  __                                                                          
                    _ __ ___   ___  _ __ | |_| |__                                                                        
                   | '_ ` _ \ / _ \| '_ \| __| '_ \                                                                       
                   | | | | | | (_) | | | | |_| | | |                                                                      
                   |_| |_| |_|\___/|_| |_|\__|_| |_|                                                                      
                                                                                                                          
     WORK.RESID  obs=48                                                                                                   
                                                                                                                          
     Obs    MONTH      RESID                                                                                              
                                                                                                                          
       1       1      0.00107                                                                                             
       2       2     -0.00322                                                                                             
       3       3     -0.00001                                                                                             
       4       4     -0.13044                                                                                             
       5       5     -0.07326                                                                                             
       6       6     -0.45350                                                                                             
       7       7      0.60959                                                                                             
       8       8      0.39125                                                                                             
       9       9      0.44056                                                                                             
      10      10     -0.20274                                                                                             
      ...                                                                                                                 
                                                                                                                          
          0        10        20        30        40        50                                                             
       +--+---------+---------+---------+---------+---------+--+                                                          
       |                                                       |                                                          
       |                 _     _             _                 |                                                          
       |   _ __ ___  ___(_) __| |_   _  __ _| |___             |                                                          
       |  | '__/ _ \/ __| |/ _` | | | |/ _` | / __|            |                                                          
     2 +  | | |  __/\__ \ | (_| | |_| | (_| | \__ \            +  2.000                                                   
       |  |_|  \___||___/_|\__,_|\__,_|\__,_|_|___/            |                                                          
       |                                                       |                                                          
       |                                          +            |                                                          
       |                                                       |                                                          
       |                 +                         +           |                                                          
       |                                                       |                                                          
     1 +                                                       +  1.000                                                   
       |                  +                         +          |                                                          
       |                         ++   +                 +      |                                                          
       |         +                                             |                                                          
       |          ++                   +         +             |                                                          
       |               +                                       |                                                          
       |                                +            +         |                                                          
     0 +   +++             +             + +             +     +  0.000                                                   
       |      ++    ++  +          +                      +    |                                                          
       |              +         +    +      +                  |                                                          
       |        +            + +    +     +     +              |                                                          
       |                    + +               ++      +        |                                                          
       |                                     +                 |                                                          
       |                                               +       |                                                          
    -1 +                                                       + -1.000                                                   
       |                                                       |                                                          
       +--+---------+---------+---------+---------+---------+--+                                                          
              0        10        20        30        40        50                                                         
                                          __  __                                                                          
                    _ __ ___   ___  _ __ | |_| |__                                                                        
                   | '_ ` _ \ / _ \| '_ \| __| '_ \                                                                       
                   | | | | | | (_) | | | | |_| | | |                                                                      
                   |_| |_| |_|\___/|_| |_|\__|_| |_|                                                                      
                                                                                                                          
                                                                                                                          
                                                                                                                          
          WORK.VARCOEF    WORK.LOGLIC  WORK.AIC   WORK.SIGMA2       WORK.COEF                                             
        --------------    -----------  --------   ----------   -------------------                                        
    Obs   MA1     SMA1     LOGLIC        AIC        SIGMA2        MA1        SMA1                                         
                                                                                                                          
     1  0.49501 0.50899   -41.7546     89.5092     0.32565     -0.82549    -0.82549                                       
     2  0.50899 0.49501                                                                                                   
                                                                                                                          
                                                                                                                          
    *          _       _   _                                                                                              
     ___  ___ | |_   _| |_(_) ___  _ __                                                                                   
    / __|/ _ \| | | | | __| |/ _ \| '_ \                                                                                  
    \__ \ (_) | | |_| | |_| | (_) | | | |                                                                                 
    |___/\___/|_|\__,_|\__|_|\___/|_| |_|                                                                                 
                                                                                                                          
    ;                                                                                                                     
                                                                                                                          
    %utl_submit_r64('                                                                                                     
    library(data.table);                                                                                                  
    library(SASxport);                                                                                                    
    library(haven);                                                                                                       
    have<-read_sas("d:/sd1/have.sas7bdat");                                                                               
    have<-ts(have$X);                                                                                                     
    predict(arima(have, order = c(3,0,0)), n.ahead = 12);                                                                 
    fit <- arima(have, order = c(0,1,1),seasonal = list(order = c(0,1,1)));                                               
    forcst<-predict(fit, n.ahead = 6);                                                                                    
    coef      <- as.data.table(fit$coef);                                                                                 
    nams<-names(fit$coef);                                                                                                
    coef=transpose(coef);                                                                                                 
    colnames(coef)<-nams;                                                                                                 
    varcoef   <- as.data.table(fit$var.coef);                                                                             
    sigma2    <- as.data.table(fit$sigma2); colnames(sigma2)="SIGMA2";                                                    
    loglik    <- as.data.table(fit$loglik); colnames(loglik)="LOGLIC";                                                    
    aic       <- as.data.table(fit$aic);    colnames(aic)="AIC";                                                          
    arma      <- as.data.table(fit$arma);   colnames(arma)="ARMA";                                                        
    residuals <- as.data.table(fit$residuals); colnames(residuals)="RESIDUAL";                                            
    forecst<-as.data.table(cbind(forcst$pred,forcst$se));                                                                 
    write.xport(forecst,coef,varcoef ,sigma2 ,loglik ,aic ,arma ,residuals ,file="d:/xpt/want.xpt");                      
    ');                                                                                                                   
                                                                                                                          
                                                                                                                          
    libname xpt xport "d:/xpt/want.xpt";                                                                                  
                                                                                                                          
    proc contents data=xpt._all_;                                                                                         
    run;quit;                                                                                                             
                                                                                                                          
    proc copy in=xpt out=work;                                                                                            
    run;quit;                                                                                                             
                                                                                                                          
    libname xpt clear;                                                                                                    
                                                                                                                          
    data resid;                                                                                                           
     retain month;                                                                                                        
     format resid 8.3;                                                                                                    
     set residual;                                                                                                        
     month=_n_;                                                                                                           
     resid=input(residual,best32.);                                                                                       
    run;quit;                                                                                                             
                                                                                                                          
                                                                                                                          
