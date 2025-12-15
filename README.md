# JK_FLIPFLOP
AIM:

To implement JK flipflop using verilog and validating their functionality using their functional tables

SOFTWARE REQUIRED:

Quartus prime

THEORY

JK Flip-Flop

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

<img width="550" height="357" alt="image" src="https://github.com/user-attachments/assets/4e1e0f82-b80d-475b-b10b-083a39445b97" />


This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

<img width="382" height="285" alt="image" src="https://github.com/user-attachments/assets/64c9bdf9-d5c9-4346-a6b2-195f13df8f06" />


Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State

<img width="515" height="435" alt="image" src="https://github.com/user-attachments/assets/4a34af8a-b7da-4252-b3a9-b28ab3a016d5" />


By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

<img width="600" height="209" alt="image" src="https://github.com/user-attachments/assets/618df8bd-3fff-4ed5-963c-5f91a1bf6bc5" />

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

#Procedure

Identify the inputs J, K, Clock, and outputs Q, Q̅.

Start from an SR flip-flop and add feedback paths from Q and Q̅ to inputs.

Define the truth table showing no change, reset, set, and toggle operations.

Implement the logic so the output changes only at the active clock edge.

Verify correct operation for all input combinations using timing simulation.

PROGRAM

```
module JK_FLIPFLOP (
    input  wire clk, rst, J, K,
    output reg  Q
);
    always @(posedge clk or posedge rst) begin
        if (rst)
            Q <= 1'b0;        // Reset
        else begin
            case ({J,K})
                2'b00: Q <= Q;        // Hold
                2'b01: Q <= 1'b0;     // Reset
                2'b10: Q <= 1'b1;     // Set
                2'b11: Q <= ~Q;       // Toggle
            endcase
        end
    end
endmodule

 ```
Developed by: 25013590

RegisterNumber: VANATHI T

#RTL LOGIC FOR FLIPFLOPS

<img width="1920" height="1020" alt="Screenshot 2025-12-15 154145" src="https://github.com/user-attachments/assets/945ecfeb-900d-423e-afb3-c0af1bce39d0" />


TIMING DIGRAMS FOR FLIP FLOPS

RESULTS:
 Implemented JK flipflop using verilog and validating their functionality using their functional tables

