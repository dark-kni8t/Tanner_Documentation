S-edit is a schematic entry tool that is used to document circuits that can be driven forward into a layout
of an integrated circuit. It also provides the ability to perform SPICE simulations of the circuits using a
simulation engine called T-SPICE. T-SPICE can be setup and invoked from with in S-edit.

Open S-Edit------------------------------------------------------------------------------------------------------------------------------------------
![1](https://user-images.githubusercontent.com/115934581/204841491-6dd07008-a9cf-49d6-b470-85e1eb7bfe47.png)

Create New Library-----------------------------------------------------------------------------------------------------------------------------------
![2](https://user-images.githubusercontent.com/115934581/204841535-15f24d2b-174f-47ae-b8ba-07eb07b1e8c3.png)

Avoid generic names like cmos,nmos etc---------------------------------------------------------------------------------------------------------------
![3](https://user-images.githubusercontent.com/115934581/204841593-17f9bba1-6068-4f5b-8472-3838ee4690d3.png)

Need to include libraries which contains the symbols for all basic circuit elements such as resistors, NMOS, capacitors, etc...----------------------
![4](https://user-images.githubusercontent.com/115934581/204841721-4875dad7-084f-4e6a-bb43-c8273c227d5b.png)

These all are the required libraries-----------------------------------------------------------------------------------------------------------------
![5](https://user-images.githubusercontent.com/115934581/204841794-a4a49ce7-9171-4bde-aec9-f1533a3a3dd2.png)

Create a New Cell------------------------------------------------------------------------------------------------------------------------------------
![6](https://user-images.githubusercontent.com/115934581/204841854-b411b1c3-ff44-437a-88db-3d49d83780ef.png)
![7](https://user-images.githubusercontent.com/115934581/204841909-0c5c5902-27a7-4744-b0a5-e0ab8cd2c5e2.png)

----------------------------------------------------------------------------------------------------------------------------------------------------
![8-1](https://user-images.githubusercontent.com/115934581/204841992-ca02de7b-e886-4630-a1d1-501727c05852.png)

We will use a nmos from transistor technology called Generic_250nm_Devices---------------------------------------------------------------------------
![8](https://user-images.githubusercontent.com/115934581/204841940-6cfe8375-9405-4413-b723-f1d4c91f79e3.png)

-----------------------------------------------------------------------------------------------------------------------------------------------------
![10](https://user-images.githubusercontent.com/115934581/204842308-850608db-0acf-4c76-ad9c-fd026e614bfc.png)

-----------------------------------------------------------------------------------------------------------------------------------------------------
![11](https://user-images.githubusercontent.com/115934581/204842346-7bd3515f-0bef-45a6-844a-0cc0318cf32b.png)

-----------------------------------------------------------------------------------------------------------------------------------------------------
![12](https://user-images.githubusercontent.com/115934581/204842394-ddb34e57-13d0-47ef-a053-19e9e3350ede.png)

In V-property, We will enter a parameter name here and then set up the parameter later. When performing a DC sweep, you must use parameters for the sweep.
![13](https://user-images.githubusercontent.com/115934581/204842429-0bfd2e2a-1f33-40eb-9d2d-ac8d33190f42.png)
![14](https://user-images.githubusercontent.com/115934581/204842498-5505b4f7-a173-4b3d-8cd0-df2ce9262032.png)

Enter a Current Probe to monitor IDS
Enter the SPICE_Plot:I_DeviceTerminalPrint component. This doesn???t connect to anything.
You just place it anywhere and then tell it what current to monitor in its properties dialog.--------------------------------------------------------
![15](https://user-images.githubusercontent.com/115934581/204842521-1ad0fd3c-261d-4fde-bcce-929fdfddd92c.png)

In its properties dialog, setup:
-Terminal: D (this is the Drain of the NMOS)
-Device: MMn1 (this is the name of the device. Notice that we called it Mn1, but S-edit automatically appends another M to the name. You will only see this once you run the Netlist. If it doesn't append, then we have to append it ourselves. Else error occurs.)
-Analysis: DC (VERY IMPORTANT TO SELECT THIS!!!!)----------------------------------------------------------------------------------------------------
![16](https://user-images.githubusercontent.com/115934581/204842537-3da009c2-c471-4054-b064-ec1b09f97c09.png)

This is the circuit----------------------------------------------------------------------------------------------------------------------------------
![17-1](https://user-images.githubusercontent.com/115934581/204842579-ded40909-9d6e-46c5-8fdb-f85971c9e20a.png)

Save the changes-------------------------------------------------------------------------------------------------------------------------------------
![17](https://user-images.githubusercontent.com/115934581/204842551-64f16017-0139-418d-b4d4-55266b8e4ca2.png)

-----------------------------------------------------------------------------------------------------------------------------------------------------

Setup the SPICE Models for the Generic_250nm_Devices kit.------------------------------------------------------------------------------------------------------
![19](https://user-images.githubusercontent.com/115934581/204842599-98672939-51ed-4e47-9c74-f09928d0bf94.png)

[The libraries that you just added have symbols for NMOS and PMOS transistors. However, all non-linear components such as MOS transistors require a model to describe their behavior. If you simply enter an NMOS symbol in your schematic, SPICE will not know what to do since each NMOS transistor fabricated in a different technology behave differently. In this example, we will use a transistor technology called ???Generic_250nm_Devices???, which represents a standard, 250nm CMOS process. You will need to setup the SPICE models for this process in S-edit. Once you do that, when you enter an NMOS or PMOS transistor, you can then associate the 250nm model to that symbol.]
-In the ???Library Files??? field, you will specify SPICE models you will be using in your simulations.
-Select DC Sweep Analysis.
![20](https://user-images.githubusercontent.com/115934581/204842624-8340653d-8bce-452a-9655-c7a01b0d4d64.png)

Setup the Parameters that will be used during the DC sweep analysis---------------------------------------------------------------------------------

![21](https://user-images.githubusercontent.com/115934581/204842639-8cea9c44-53b6-4bd2-b1fa-013370c6bb8b.png)

Setup the SPICE DC Sweep Analysis--------------------------------------------------------------------------------------------------------------------
![22](https://user-images.githubusercontent.com/115934581/204842674-8f972b2f-d377-4e6b-bbed-10283840ae31.png)

Click on the Green Arrow to start the simulator----------------------------------------------------------------------------------------------------
![23](https://user-images.githubusercontent.com/115934581/204842704-62a34e9f-7ef7-4f55-b180-5f69b31966af.png)

The T-Spice window will appear. If everything is OK, the waveform viewer will also appear. If everything worked, your waveforms should look like this
![24](https://user-images.githubusercontent.com/115934581/204842746-babee59b-44e0-4e63-9b9f-d760157dde10.png)

View the Netlist-------------------------------------------------------------------------------------------------------------------------------------
![25](https://user-images.githubusercontent.com/115934581/204842782-90020e42-485c-4539-892b-f4e912fafcb5.png)

-----------------------------------------------------------------------------------------------------------------------------------------------------
![26](https://user-images.githubusercontent.com/115934581/204842806-06866e15-981a-4b32-bed5-291744aa5a8a.png)

-----------------------------------------------------------------------------------------------------------------------------------------------------
![27](https://user-images.githubusercontent.com/115934581/204842847-73b8f16e-04fc-442e-b80c-5c91323a148c.png)

----------------------------------------------------------------------------finish------------------- ------------------------------------------------
