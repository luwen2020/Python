"""
This code can help you download the ERA-Interim data from ECMWF database.
It can download not only surface but also sounding data.
Please run on python3
2018-12-10 16:56 : Created by Lu Wen ,Nuist .
E-mail:luw1996@163.com
If you have any questions , we can communicate by E-mail.
"""
#!/usr/bin/env python
from ecmwfapi import ECMWFDataServer
import time
"""    Time  Preprocess"""
def convert_time(aa):
    aa=str(aa)
    a=time.strptime(aa, "%Y%m%d")
    return time.strftime("%Y-%m-%d",a)
print("Please enter the start_date and end_date! Such as 20180101.")
start=input("start_date=  ")
end  =input("end_date  =  ")
start_time=convert_time(start)
end_time=convert_time(end)
"""------------------------------------------------------------"""

"""                 Download the data                          """
server = ECMWFDataServer()
"""-----------------  surface ---------------------------------"""
server.retrieve({
    "class": "ei",
    "dataset": "interim",
    "date": start_time+"/to/"+end_time,
    "expver": "1",
    "grid": "0.75/0.75",
    "levtype": "sfc",
    "param": """
                 31.128/32.128/33.128/34.128/
                 35.128/36.128/37.128/38.128/
                 39.128/40.128/41.128/42.128/
                 53.162/54.162/55.162/56.162/
                 57.162/58.162/59.162/60.162/
                 61.162/62.162/63.162/64.162/
                 65.162/66.162/67.162/68.162/
                 69.162/70.162/71.162/72.162/
                 73.162/74.162/75.162/76.162/
                 77.162/78.162/79.162/80.162/
                 81.162/82.162/83.162/84.162/
                 85.162/86.162/87.162/88.162/
                 89.162/90.162/91.162/92.162/
                 134.128/136.128/137.128/139.128/
                 141.128/148.128/151.128/164.128/
                 165.128/166.128/167.128/168.128/
                 170.128/173.128/174.128/183.128/
                 186.128/187.128/188.128/198.128/
                 206.128/234.128/235.128/236.128/
                 238.128/229.140/230.140/232.140
             """,                                      
    "step": "0",
    "stream": "oper/wave",
    "time": "00:00:00/06:00:00/12:00:00/18:00:00",
    "type": "an",
    "target": "surface-"+start_time+"-to-"+end_time+".grib",
})
"""------------------------------------------------"""

"""------------------ high    ---------------------"""
server.retrieve({
    "class": "ei",
    "dataset": "interim",
    "date": start_time+"/to/"+end_time,
    "expver": "1",
    "grid": "0.75/0.75",
    "levelist": """
                    1/2/3/5/7/10/20/30/50/70/
                    100/125/150/175/200/225/
                    250/300/350/400/450/500/
                    550/600/650/700/750/775/
                    800/825/850/875/900/925/
                    950/975/1000""",
    "levtype": "pl",
    "param": """
                 60.128/129.128/130.128/
                 131.128/132.128/133.128/
                 135.128/138.128/155.128/
                 157.128/203.128/246.128/
                 247.128/248.128""",
    "step": "0",
    "stream": "oper",
    "time": "00:00:00/06:00:00/12:00:00/18:00:00",
    "type": "an",
    "target": "high-"+start_time+"-to-"+end_time+".grib",
})
"""-------------------------------------------------"""
