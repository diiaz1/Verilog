module controladorMemoria(Rst, DataIN, Address, ReadEnable, WriteEnable, Clock, DataOut)

input DataIN, Adress, ReadEnable, WriteEnable, Clock;
reg [3:0] e_a, [3:0] e_f; 
output DataOut;

Acumulador inst_Acumulador (

//Atualizaçao do Estado Atual
always @ (posedge clock)
  begin
    if (Rst)
      begin
        e_a <= IDLE;
      end
    else
      begin
        e_a <= e_f;
      end

//Decodificador de próximo estado
always (*)
  begin
    case(e_a)
      
  
  end
  
  
