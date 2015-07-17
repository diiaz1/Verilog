module Acumulador (M, LOAD, CLEAR, TRANSFER, N)

  input [3:0] M, LOAD, CLEAR, TRANSFER;
  output [3:0] N;
  reg [3:0] A, [3:0] B;
  wire [3:0] S;
  
  if (CLEAR == 0)
    begin
      A = 4'b0;
    end
  
  else
    begin
    
      always @ (posedge LOAD)
        begin
          assign B = M;
          assign S = A + B;
        end
      
    always @ (posedge TRANSFER)
      begin
        assign A = S;
        assign N = A;
      end
      
    end
