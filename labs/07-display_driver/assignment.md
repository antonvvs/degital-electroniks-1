# Lab 7: Tsyhanov Anton 230336

### Display driver

1. Listing of VHDL code of the completed process `p_mux`. Always use syntax highlighting, meaningful comments, and follow VHDL guidelines:

```vhdl
   p_mux : process(clk)
    begin
        if rising_edge(clk) then
            if (reset = '1') then
                s_hex <= data0_i;
                dp_o  <= dp_i(0);
                dig_o <= "1110";
            else
                case s_cnt is
                    when "11" =>
                        s_hex <= data3_i;
                        dp_o  <= dp_i(3);
                        dig_o <= "0111";

                    when "10" =>
                       
                        s_hex <= data2_i;
                        dp_o  <= dp_i(2);
                        dig_o <= "1011";
                   
                    when "01" =>
                       
                        s_hex <= data1_i;
                        dp_o  <= dp_i(1);
                        dig_o <= "1101";
                  
                    when others =>
                        
                        s_hex <= data0_i;
                        dp_o  <= dp_i(0);
                        dig_o <= "1110";
               
                end case;
            end if;
        end if;
    end process p_mux;

```

2. Screenshot with simulated time waveforms. Test reset as well. Always display all inputs and outputs (display the inputs at the top of the image, the outputs below them) at the appropriate time scale!

![image](https://user-images.githubusercontent.com/99277478/160632969-18afcdcf-7186-482f-8119-5aa970f76b37.png)

### Eight-digit driver

1. Image of the 8-digit driver's block schematic. The image can be drawn on a computer or by hand. Always name all inputs, outputs, components, and internal signals!

   ![image](https://user-images.githubusercontent.com/99277478/161596192-56fe344a-2be8-45c2-82d4-a26415e228db.png)
