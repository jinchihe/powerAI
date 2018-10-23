# Installing PowerAI frameworks

1. Set up the software repository, the RPM file was extracted when you ran the PowerAI Enterprise install bin file.
```
   rpm -ihv mldl-repo-*.rpm  
```  

2. Install all PowerAI frameworks.
```
   yum install power-mldl
```  
3. (Optional) Install PowerAI Distributed Deep Learning (DDL) packages.
```
   yum install power-ddl
```
 
4. (Optional) Install PowerAI SnapML packages.
```
   yum install power-snapml
```
