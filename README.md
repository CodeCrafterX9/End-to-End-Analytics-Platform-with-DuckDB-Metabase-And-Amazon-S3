# End-to-End-Analytics-Platform-with-DuckDB-Metabase
A complete analytics solution using DuckDB as the analytical database and Metabase as business intelligence (BI) layer. We'll ingest and model data in DuckDB using Pyspark, automate updates using GitHub Actions, and create interactive dashboards in Metabase for business users.


Dekho docker container run karne ke liye :- 
docker run -d -p 3000:3000 metabase/metabase
isse metabase ka imge download hoke run ho jaega ya directly container ban jaega

then o ye port map hua hai ye abhi public nahi hai --> uske lie
gh codespace ports visibility 3000:public
isse pulic ho jaega 
then press enter 


JUPYTER LAB WALI IMAGE BUILD KARNE KE LIYE 
make sure you are in 
root folder 
-> cd ./setup/jupyter_lab
-> docker build -t jupyter_image .
-> docker images   #check karo isse image bani nahi bani 
-> docker run -it --entrypoint=bash -p 8888:8888 jupyter_image 
-> jupyter lab --ip=0.0.0.0 --allow-root --no-browser   # for running jupyter lab 
--> jupyter lab --ip=0.0.0.0 --allow-root --no-browser --NotebookApp.token='' --NotebookApp.password=''      #for bypassing token

Dekho docker compose agar chalana hai decker ke liye 
to 
-> cd ./setup

fir usse docker iamge banane ke liye :
docker compose up --build