/ # hbase shell
2023-03-16 17:50:10,648 WARN  [main] util.NativeCodeLoader: Unable to load native-hadoop library for your platform... using builtin-java classes where applicable
HBase Shell; enter 'help<RETURN>' for list of supported commands.
Type "exit<RETURN>" to leave the HBase Shell
Version 1.3.2, r1bedb5bfbb5a99067e7bc54718c3124f632b6e17, Mon Mar 19 18:47:19 UTC 2018

hbase(main):001:0> create 'stu_details','bio','marks','details'
0 row(s) in 1.9210 seconds

=> Hbase::Table - stu_details
hbase(main):002:0> list
TABLE                                                                                                                                                           
stu_details                                                                                                                                                         
1 row(s) in 0.0810 seconds

=> ["stu_details"]
hbase(main):003:0> put 'stu_details','01','bio:name','Poornisha'
0 row(s) in 0.3050 seconds

hbase(main):004:0> put 'stu_details','01','bio:id','81'
0 row(s) in 0.0290 seconds

hbase(main):005:0> put 'stu_details','01','bio:mobileno','9080885297'
0 row(s) in 0.0500 seconds

hbase(main):006:0> put 'stu_details','01','bio:email','poornishakathirvel@gmail.com'
0 row(s) in 0.0520 seconds

hbase(main):008:0> put 'stu_details','01','marks:10th','460'
0 row(s) in 0.0680 seconds

hbase(main):009:0> put 'stu_details','01','marks:12th','446'
0 row(s) in 0.0200 seconds

hbase(main):010:0> put 'stu_details','01','details:hostel/dayschalor','hostel'
0 row(s) in 0.0900 seconds

hbase(main):011:0> put 'stu_details','01','details:fees','100000/-'
0 row(s) in 0.0120 seconds

hbase(main):012:0> put 'stu_details','02','bio:name','sowndhariya'
0 row(s) in 0.0270 seconds

hbase(main):013:0> put 'stu_details','02','bio:id','98'
0 row(s) in 0.0770 seconds

hbase(main):014:0> put 'stu_details','02','bio:dob','16/12/2002'
0 row(s) in 0.0980 seconds

hbase(main):009:0> put 'stu_details','02','marks:12th','459'
0 row(s) in 0.0590 seconds

hbase(main):015:0> put 'stu_details','02','details:fees','60000/-'
0 row(s) in 0.0540 seconds

hbase(main):016:0> put 'stu_details','03','bio:name','abi'
0 row(s) in 0.0250 seconds

hbase(main):017:0> put 'stu_details','03','bio:fathername','vel'
0 row(s) in 0.0200 seconds

hbase(main):018:0> put 'stu_details','03','bio:id','17'
0 row(s) in 0.0490 seconds

hbase(main):019:0> put 'stu_details','03','marks:12th','567'
0 row(s) in 0.0250 seconds

hbase(main):020:0> put 'stu_details','03','marks:CGPA','9.21'
0 row(s) in 0.0390 seconds

hbase(main):021:0> put 'stu_details','03','details:fees','26000/-'
0 row(s) in 0.0200 seconds

hbase(main):021:0> put 'stu_details','03','details:MQ/GQ','GQ'
0 row(s) in 0.0450 seconds

hbase(main):022:0> get 'stu_details','01'
COLUMN                                    CELL                                                                                                                  
 bio:name                                 timestamp=1678990472589, value=poornisha                                                                                 
 bio:id                                   timestamp=1678990435991, value=81                                                                              
 bio:mobileno                             timestamp=1678990078779, value=9080885297                                                                               
 bio:email                                timestamp=1678990151721, value=poornishakathirvel@gmail.com                                                                                                                                                      
 details:hosteller/dayscholar             timestamp=1678990377698, value=hostel                                                                                
 details:fees                             timestamp=1678990340801, value=100000/-
 marks:10th                               timestamp=1678990107273, value=460                                                                             
 marks:12th                               timestamp=1678989957023, value=446                                                                               
1 row(s) in 0.1790 seconds

hbase(main):023:0> get 'stu_details','02'
COLUMN                                    CELL                                                                                                                  
 bio:name                                 timestamp=1678990877495, value=sowndhariya                                                                                
 bio:id                                   timestamp=1678990697077, value=98                                                                       
 bio:dob                                  timestamp=1678990789753, value=16/12/2002                                                                             
 details:fees                             timestamp=1678990632340, value=60000/- 
 marks:12th                               timestamp=1678990676540, value=459                                                   
1 row(s) in 0.0590 seconds

hbase(main):024:0> get 'stu_details','03'
COLUMN                                    CELL                                                                                                                  
 bio:name                                 timestamp=1678991191832, value=abi                                                                                
 bio:fathername                           timestamp=1678991043431, value=vel                                                                           
 bio:id                                   timestamp=1678990957427, value=17                                                                                
 details:fees                             timestamp=1678990989731, value=26000/-                                                                                    
 details:MQ/GQ                            timestamp=1678991104761, value=GQ                                                                                 
 marks:12th                               timestamp=1678991138389, value=567 
 marks:CGPA                               timestamp=1678991138389, value=9.21                                                                             
1 row(s) in 0.0720 seconds

hbase(main):025:0> scan 'family'
ROW                                       COLUMN+CELL                                                                                                           
 01                                       column=bio:name,timestamp=1678990472589, value=poornisha                              
 01                                       column=bio:id,timestamp=1678990435991, value=81                                                       
 01                                       column=bio:mobileno,timestamp=1678990078779, value=9080885297                                                
 01                                       column=bio:email,timestamp=1678990151721, value=poornishakathirvel@gmail.com                                                 
 01                                       column=details:hosteller/dayscholar,timestamp=1678990377698, value=hostel           
 01                                       column=details:fees,timestamp=1678990340801, value=100000/-                                                          
 01                                       column=marks:10th,timestamp=1678990107273, value=460                                                       
 01                                       column=marks:12th,timestamp=1678989957023, value=446                                                       
 02                                       column=bio:name,timestamp=1678990877495, value=sowndhariya                                                            
 02                                       column=bio:id,timestamp=1678990697077, value=98                                                       
 02                                       column=bio:dob,timestamp=1678990789753, value=16/12/2002                                                         
 02                                       column=details:fees,timestamp=1678990632340, value=60000/- 
 02                                       column=marks:12th,timestamp=1678990676540, value=459 
 03                                       column= bio:name,timestamp=1678991191832, value=abi                                                         
 03                                       column=bio:fathername,timestamp=1678991043431, value=vel                                                     
 03                                       column=bio:id,timestamp=1678990957427, value=17                                                              
 03                                       column=details:fees,timestamp=1678990989731, value=26000/-                                                            
 03                                       column=details:MQ/GQ,timestamp=1678991104761, value=GQ                                                                  
 03                                       column= marks:12th,timestamp=1678991138389, value=567 
 03                                       column=marks:CGPA,timestamp=1678991138389, value=9.21                                                                 
3 row(s) in 0.2030 seconds

hbase(main):026:0> put 'stu_details','01','bio:mobileno','9976370389'
0 row(s) in 0.0180 seconds

hbase(main):027:0> get 'stu_details','01'
COLUMN                                    CELL                                                                                                                  
 bio:name                                 timestamp=1678990472589, value=poornisha                                                                                 
 bio:id                                   timestamp=1678990435991, value=81                                                                              
 bio:mobileno                             timestamp=1678990078779, value=9976370389                                                                               
 bio:email                                timestamp=1678990151721, value=poornishakathirvel@gmail.com                                                                                                                                                      
 details:hosteller/dayscholar             timestamp=1678990377698, value=hostel                                                                                
 details:fees                             timestamp=1678990340801, value=100000/-
 marks:10th                               timestamp=1678990107273, value=460                                                                             
 marks:12th                               timestamp=1678989957023, value=446                                                                                
1 row(s) in 0.0910 seconds

hbase(main):028:0> put 'stu_details','02','marks:CGPA','8.67'
0 row(s) in 0.0750 seconds

hbase(main):029:0> get 'stu_details','02'
COLUMN                                    CELL                                                                                                                  
bio:name                                  timestamp=1678990877495, value=sowndhariya                                                                                
 bio:id                                   timestamp=1678990697077, value=98                                                                       
 bio:dob                                  timestamp=1678990789753, value=16/12/2002                                                                             
 details:fees                             timestamp=1678990632340, value=60000/- 
 marks:12th                               timestamp=1678990676540, value=459   
 marks:CGPA                               timestamp=1678984504761, value=8.67                                           
1 row(s) in 0.0670 seconds

hbase(main):030:0> delete 'stu_details','03','MQ/GQ:GQ'
0 row(s) in 0.0450 seconds

hbase(main):031:0> get 'stu_details','03'
COLUMN                                    CELL                                                                                                                  
 bio:name                                 timestamp=1678991191832, value=abi                                                                                
 bio:fathername                           timestamp=1678991043431, value=vel                                                                           
 bio:id                                   timestamp=1678990957427, value=17                                                                                
 details:fees                             timestamp=1678990989731, value=26000/-                                                                                                                                                                     
 marks:12th                               timestamp=1678991138389, value=567 
 marks:CGPA                               timestamp=1678991138389, value=9.21                                                                           
1 row(s) in 0.0540 seconds

hbase(main):032:0> scan 'stu_details'
ROW                                       COLUMN+CELL                                                                                                           
 01                                       column=bio:name,timestamp=1678990472589, value=poornisha                              
 01                                       column=bio:id,timestamp=1678990435991, value=81                                                       
 01                                       column=bio:mobileno,timestamp=1678990078779, value=9976370389                                                
 01                                       column=bio:email,timestamp=1678990151721, value=poornishakathirvel@gmail.com                                                 
 01                                       column=details:hosteller/dayscholar,timestamp=1678990377698, value=hostel           
 01                                       column=details:fees,timestamp=1678990340801, value=100000/-                                                          
 01                                       column=marks:10th,timestamp=1678990107273, value=460                                                       
 01                                       column=marks:12th,timestamp=1678989957023, value=446                                                       
 02                                       column=bio:name,timestamp=1678990877495, value=sowndhariya                                                            
 02                                       column=bio:id,timestamp=1678990697077, value=98                                                       
 02                                       column=bio:dob,timestamp=1678990789753, value=16/12/2002                                                         
 02                                       column=details:fees,timestamp=1678990632340, value=60000/- 
 02                                       column=marks:12th,timestamp=1678990676540, value=459 
 02                                       column=marks:CGPA,timestamp=1678991138389, value=8.67
 03                                       column= bio:name,timestamp=1678991191832, value=abi                                                         
 03                                       column=bio:fathername,timestamp=1678991043431, value=vel                                                     
 03                                       column=bio:id,timestamp=1678990957427, value=17                                                              
 03                                       column=details:fees,timestamp=1678990989731, value=26000/-                                                            
 03                                       column= marks:12th,timestamp=1678991138389, value=567 
 03                                       column=marks:CGPA,timestamp=1678991138389, value=9.21                                                                   
3 row(s) in 0.1550 seconds

hbase(main):033:0> 
