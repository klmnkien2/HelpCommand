Linux
===========
top –c : dùng để xem thông tin hoạt động của server
free –m : dùng để kiểm tra thông tin bộ nhớ
df –h : dùng để kiểm tra dụng lượng ổ cứng
sync; echo 3 > /proc/sys/vm/drop_caches : dùng để giải phóng caches và làm tăng bộ nhớ

Oracle
===========
su – oracle  (dùng để vào oracle)
sqlplus / as sysdba
startup
SHUTDOWN IMMEDIATE

create user HSCV_THA identified by HSCV_THA;
grant dba to HSCV_THA;

CREATE DIRECTORY DMPDIR as '/u02/dmpdir'; //create directory for importdb/exportdb

import & export
expdp HSCV_BTP_FINAL/HSCV_BTP_FINAL schemas=HSCV_BTP_FINAL directory=DMPDIR dumpfile=file.dmp logfile=export.log
impdp HSCV_NEW/HSCV_NEW  REMAP_SCHEMA=HSCV_FINAL:HSCV_NEW directory=DMPDIR dumpfile=file.dmp logfile=import.log

