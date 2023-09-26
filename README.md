# Full Custom Design of Peripheral circuitry for 8x8 SRAM Block

You can find the first half of this repo already comitted here. https://github.com/ChandanS15/Comparative-Analysis-of-Decoders-using-Static-Dynamic-CMOS-Logic.git

I have also icluded a detailed report on how each circuit works and why they were eventually chosen to implement the final block.

> ```SKILL

;;;########################################################
;;;#	Author	: Chandan Srinivas	
;;;#	Date	: 24-06-2023
;;;#          load "create_arr.il"
;;;#          create_arr("libname" "cellname" 128 128) 
;;;#
;;;#########################################################

procedure(create_arr(lib cellview M N)
	;prog(bBox,ur,ll,urx,ury,llx,lly,dx,dy,cv,cvi)
	; Open cellview to write
	cv = dbOpenCellViewByType(lib "Array_Output" "layout" "maskLayout" "w")
	printf("\n%s opened" cellview)

	;open the layout of SRAM to be used
	cvi = dbOpenCellViewByType(lib cellview "layout")



; use bbox to get the dimensions 
; prBoundary is now BOUNDARY in the 2018 ASAP 7nm PDK
prb=cvi~>prBoundary~>bBox
        
ur=upperRight(prb)
ll=lowerLeft(prb)
urx=xCoord(ur)
ury=yCoord(ur)
llx=xCoord(ll)
lly=yCoord(ll)

;dx is the width of the cell and dy is the height of the cell
dx=urx-llx;
dy=ury-lly;

;creating the MxN array with alternate rows reversed to share common vdd and ground
for(row 0 M
for(column 0 N
 
  dbCreateInst( cv cvi "" list(column*dx row*dy) "R0")


)
)
dbClose(cvi)
	dbSave(cv)
	dbClose(cv)

)





```

![image](https://github.com/ChandanS15/Full-Custom-Design-of-Peripheral-circuitry-for-8x8-SRAM-Block/assets/82103081/501893c7-f021-4c89-9767-9a0f4a581227)



![image](https://github.com/ChandanS15/Full-Custom-Design-of-Peripheral-circuitry-for-8x8-SRAM-Block/assets/82103081/ca087616-4a0d-472e-b98a-d5c7a65b163a)



![image](https://github.com/ChandanS15/Full-Custom-Design-of-Peripheral-circuitry-for-8x8-SRAM-Block/assets/82103081/da199f75-bbc0-4cb3-a1cd-58cdd459dafc)



![image](https://github.com/ChandanS15/Full-Custom-Design-of-Peripheral-circuitry-for-8x8-SRAM-Block/assets/82103081/7a3a0393-9a88-4340-a8b8-1b002f953ebb)



![image](https://github.com/ChandanS15/Full-Custom-Design-of-Peripheral-circuitry-for-8x8-SRAM-Block/assets/82103081/4c469321-5ba9-4dcc-ac5d-5048135502a5)



![image](https://github.com/ChandanS15/Full-Custom-Design-of-Peripheral-circuitry-for-8x8-SRAM-Block/assets/82103081/0b53389c-bf21-4dc7-abda-668c81d2e51e)



![image](https://github.com/ChandanS15/Full-Custom-Design-of-Peripheral-circuitry-for-8x8-SRAM-Block/assets/82103081/68e6e8a0-223b-4718-a195-195d3ac5cf29)



![image](https://github.com/ChandanS15/Full-Custom-Design-of-Peripheral-circuitry-for-8x8-SRAM-Block/assets/82103081/812669f5-9bdb-4fad-9a15-dccbeb37a05d)



![image](https://github.com/ChandanS15/Full-Custom-Design-of-Peripheral-circuitry-for-8x8-SRAM-Block/assets/82103081/45dd86b8-300a-4fc3-a45c-d0afc2b88bc3)



![image](https://github.com/ChandanS15/Full-Custom-Design-of-Peripheral-circuitry-for-8x8-SRAM-Block/assets/82103081/be057c2c-37b1-4a36-852c-13fed6e7e5ea)



![image](https://github.com/ChandanS15/Full-Custom-Design-of-Peripheral-circuitry-for-8x8-SRAM-Block/assets/82103081/9ea56c7b-ecdf-4e1d-9306-a53bf598a74b)



![image](https://github.com/ChandanS15/Full-Custom-Design-of-Peripheral-circuitry-for-8x8-SRAM-Block/assets/82103081/0af217f9-4e3c-4ada-8345-c87e40241f2b)



![image](https://github.com/ChandanS15/Full-Custom-Design-of-Peripheral-circuitry-for-8x8-SRAM-Block/assets/82103081/0878abfc-b31f-4216-93b1-3c66e1953eb7)



![image](https://github.com/ChandanS15/Full-Custom-Design-of-Peripheral-circuitry-for-8x8-SRAM-Block/assets/82103081/f5a2dbee-454b-4ab9-a46b-de34f817652c)



![image](https://github.com/ChandanS15/Full-Custom-Design-of-Peripheral-circuitry-for-8x8-SRAM-Block/assets/82103081/a4458cec-46f3-4acd-a7f8-571c424fadf8)



![image](https://github.com/ChandanS15/Full-Custom-Design-of-Peripheral-circuitry-for-8x8-SRAM-Block/assets/82103081/020d2559-3457-4aba-bc80-54383e988d38)



![image](https://github.com/ChandanS15/Full-Custom-Design-of-Peripheral-circuitry-for-8x8-SRAM-Block/assets/82103081/67d1beaf-7601-4bc8-815b-e12093323c20)



![Screenshot 2023-08-13 170150](https://github.com/ChandanS15/Full-Custom-Design-of-Peripheral-circuitry-for-8x8-SRAM-Block/assets/82103081/a6cc3d7e-ee5e-4303-8e69-347dfceeb0ac)



![image](https://github.com/ChandanS15/Full-Custom-Design-of-Peripheral-circuitry-for-8x8-SRAM-Block/assets/82103081/0cb3b508-0675-45cc-9ac9-00704d3aa63e)



![image](https://github.com/ChandanS15/Full-Custom-Design-of-Peripheral-circuitry-for-8x8-SRAM-Block/assets/82103081/e8a6af85-38d2-47ea-9d73-f4321cfb83e9)



![image](https://github.com/ChandanS15/Full-Custom-Design-of-Peripheral-circuitry-for-8x8-SRAM-Block/assets/82103081/46bb750b-ce41-45bd-8217-306d1755677b)


![image](https://github.com/ChandanS15/Full-Custom-Design-of-Peripheral-circuitry-for-8x8-SRAM-Block/assets/82103081/36af15dd-4171-40b2-abd0-5880011ce2dc)


![image](https://github.com/ChandanS15/Full-Custom-Design-of-Peripheral-circuitry-for-8x8-SRAM-Block/assets/82103081/f236cec7-1be6-4319-b1e8-30bff21887d9)



![image](https://github.com/ChandanS15/Full-Custom-Design-of-Peripheral-circuitry-for-8x8-SRAM-Block/assets/82103081/e34d0dce-2019-4dd8-bbb1-5f0bc2a59074)



![Untitled](https://github.com/ChandanS15/Full-Custom-Design-of-Peripheral-circuitry-for-8x8-SRAM-Block/assets/82103081/76786164-970f-46f8-99ec-394468c61f89)




![image](https://github.com/ChandanS15/Full-Custom-Design-of-Peripheral-circuitry-for-8x8-SRAM-Block/assets/82103081/167ee750-6695-4b32-8a0b-730f4611ee06)



![image](https://github.com/ChandanS15/Full-Custom-Design-of-Peripheral-circuitry-for-8x8-SRAM-Block/assets/82103081/a9b9f5ea-f30d-44db-8e87-2660349d9900)



![image](https://github.com/ChandanS15/Full-Custom-Design-of-Peripheral-circuitry-for-8x8-SRAM-Block/assets/82103081/548b1c09-5a80-44f3-b1e0-75e4748f23ff)



![image](https://github.com/ChandanS15/Full-Custom-Design-of-Peripheral-circuitry-for-8x8-SRAM-Block/assets/82103081/aa5a02ed-0540-4100-948a-b5df2668ea3f)




![image](https://github.com/ChandanS15/Full-Custom-Design-of-Peripheral-circuitry-for-8x8-SRAM-Block/assets/82103081/417d836b-53d3-46a0-acdf-608a367894aa)




![image](https://github.com/ChandanS15/Full-Custom-Design-of-Peripheral-circuitry-for-8x8-SRAM-Block/assets/82103081/2c125586-8fb9-4c6b-8aa1-a434659f4f44)




![image](https://github.com/ChandanS15/Full-Custom-Design-of-Peripheral-circuitry-for-8x8-SRAM-Block/assets/82103081/31a450a1-aada-4283-a3ef-dd8e05277191)
