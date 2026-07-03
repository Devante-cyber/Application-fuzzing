# Application-fuzzing
Understand the security concerns associated with application vulnerabilities.

•	Select ZYWIN01 from the drop-down menu in the right pane and click Connect to VMs.

•	Click Windows Start and click the vulnserver icon that appears in Windows Start. Vulnserver opens a command prompt window that must remain open.

 <img width="975" height="759" alt="image" src="https://github.com/user-attachments/assets/117352bb-317d-41c4-9fb9-cb8644962e1a" />

• vulnserver waits for client connections.

<img width="1056" height="763" alt="image" src="https://github.com/user-attachments/assets/d465927f-4027-4c83-bb6d-25bf59bbc040" />

// Task 2: Execute Spike fuzzing scripts from ZYKALI01

• Select ZYKALI01 from the drop-down menu in the right pane.

• Click the Terminal Emulator icon in the top menu bar to open the terminal emulator.

• The terminal emulator executes a command when the Enter key is pressed. Execute a netcat (nc) command to verify connectivity to vulnserver running on ZYWIN01:

<img width="268" height="45" alt="image" src="https://github.com/user-attachments/assets/eeac85e5-1d3a-48eb-8416-a9b8a4b3e3ab" />

• Netcat executed 

<img width="1005" height="788" alt="image" src="https://github.com/user-attachments/assets/d7aaebfa-debe-4e9f-a219-7ed894f84f87" />

•Type EXIT and press the Enter key to exit the nc command.

<img width="988" height="746" alt="image" src="https://github.com/user-attachments/assets/5eeacf04-0493-4a3a-bec1-92df89ea678c" />

Open the Kali application menu in the top left corner of the screen. Click 02-Vulnerability Analysis,

<img width="920" height="788" alt="image" src="https://github.com/user-attachments/assets/3d998f3e-1156-4fc6-a23d-e14da49f1b85" />

click Fuzzing Tools, and click spike-generic_send_tcp. 

<img width="668" height="704" alt="image" src="https://github.com/user-attachments/assets/2f4f9281-76d3-4abb-8fb8-b8ef3573c959" />

A new Terminal Emulator window opens with information on executing the spike-generic_send_tcp script

<img width="883" height="656" alt="image" src="https://github.com/user-attachments/assets/5c8453c3-5aa6-43e3-b81a-691215d835be" />

Execute the smtp1.spk script by typing:
generic_send_tcp ZYWIN01 9999 /usr/share/spike/audits/SMTP/smtp1.spk 0 0

<img width="648" height="473" alt="image" src="https://github.com/user-attachments/assets/7fe58481-26d1-4da3-8228-0ea1c7ce7614" />

 Click 02-Vulnerability Analysis, click Fuzzing Tools,

 <img width="586" height="663" alt="image" src="https://github.com/user-attachments/assets/a73710e5-15ed-48d8-8aa9-02a8dea16c9c" />

  click spike-generic_send_udp. A new Terminal Emulator window opens with information on executing the spike-generic_send_udp script.

<img width="589" height="580" alt="image" src="https://github.com/user-attachments/assets/3eb19421-eb19-4604-9923-cff6b8ffb96d" />

Execute the spike-generic_send_udp script with an pop3.spk script by typing:
generic_send_udp ZYWIN01 9999 /usr/share/spike/audits/POP3/pop3.spk 0 0 5000

<img width="632" height="375" alt="image" src="https://github.com/user-attachments/assets/884707d7-6156-4472-8540-9cf07a89eb8f" />

Review the output captured in the vulnserver command prompt. The output is the result of the spike-generic_send_tcp fuzzing and spike-generic_send_udp scripts. 
The earlier SMTP and POP3 commands were sent successfully.

<img width="914" height="507" alt="image" src="https://github.com/user-attachments/assets/6168d48d-5468-483e-a33f-1dfc0016c00f" />

// Execute the following command to open a text editor to create a custom Spike fuzzing script called trun.spk:

<img width="187" height="50" alt="image" src="https://github.com/user-attachments/assets/77fecf55-70ad-4e79-bd9c-9c1f3b8ea55a" />

Type the following lines into the script's body:

s_readline();

s_string("TRUN ");

s_string_variable("COMMAND");

<img width="283" height="151" alt="image" src="https://github.com/user-attachments/assets/8e07fa37-e1b4-4ad2-9d24-7bb070206046" />










