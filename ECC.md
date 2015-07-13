'timescale 1ns/ns

module ECC_tb(R_W, m, x);
  reg R_W_tb, [8:1] m_tb;
  wire [12:1] x_tb;
	
	reg [4:1] k_tb;
	integer indice_tb;

  ECC ECC_INST (.R_W(R_W_tb), .m(m_tb), .x(x_tb), .k(k_tb), .indice (indice_tb));

	//Trabalhando com todas as combinações possíveis -> 256 entradas diferentes 
	
	initial
	  begin
	    $display("Gerando o código de Hamming da palavra de entrada");
	    $display("\tTempo \tm_tb[8] \tm_tb[7] \tm_tb[6] \tm_tb[5] \tm_tb[4] \tm_tb[3] \tm_tb[2] \tm_tb[1] \tx_tb[12] \tx_tb[11] \tx_tb[10] \tx_tb[9] \tx_tb[8] \tx_tb[7] \tx_tb[6] \tx_tb[5] \tx_tb[4] \tx_tb[3] \tx_tb[2] \tx_tb[1]");
	    $monitor("\t%t \t%b \t%b \t%b \t%b \t%b \t%b \t%b \t%b   \t%b \t%b \t%b \t%b \t%b \t%b \t%b \t%b \t%b \t%b \t%b \t%b",
	             $time, m_tb[8], m_tb[7], m_tb[6], m_tb[5], m_tb[4], m_tb[3], m_tb[2], m_tb[1],
	             x_tb[12], x_tb[11], x_tb[10], x_tb[9], x_tb[8], x_tb[7], x_tb[6], x_tb[5], x_tb[4], x_tb[3], x_tb[2], x_tb[1]);
	    
	    for (i = 0; i < 256; i = i + 1)
	      begin
	        m = i;
	        #100
	      end
	   
	   $stop;
	   end

endmodule

