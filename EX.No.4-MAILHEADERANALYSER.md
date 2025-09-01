                                                               //EXPERIMENT - 4//

                                                                    //MHA//

                                                             //Mail Header Analyzer//

**Link:-** <https://mxtoolbox.com/EmailHeaders.aspx>

**Procedure**

**Step 1: Get the Email Header**

-   First, you need to copy the full, raw header from the email.

-   Gmail: Open the email, click the three dots (⋮), and select Show
    original.

-   Select all the text in the header and copy it.

-   <img width="1905" height="968" alt="Screenshot (71)" src="https://github.com/user-attachments/assets/06317788-6311-4ffa-a468-1c3d4584f57c" />
    <img width="1920" height="968" alt="Screenshot (72)" src="https://github.com/user-attachments/assets/e3e6f312-c30d-4523-b7e3-adfce6d32211" />
    <img width="1920" height="968" alt="Screenshot (73)" src="https://github.com/user-attachments/assets/5bbdee8a-7703-42ee-96f4-7d71ca48892e" />

-   
  

**Step 2: Use a Mail Header Analyzer**

-   The easiest way to analyze the header is with an online tool.

-   Navigate to a site which analyze Email Header

-   Paste the entire header you copied into the analysis box.

-   Click the \"Analyze\" button to get a parsed, easy-to-read report.

-  <img width="1358" height="632" alt="Image" src="https://github.com/user-attachments/assets/ebb0ab60-2b91-47d3-8b16-bfe76297e337" />

> **Step 3: Analyze The Report**

-   This is the most critical step. In the analyzer\'s report, look for
    the SPF, DKIM, and DMARC results.

    <img width="1920" height="978" alt="Screenshot (74)" src="https://github.com/user-attachments/assets/1c01e764-791c-437a-90fd-7b60804a8df4" />


    

**Review the Overall Delivery Summary**

-   First, look at the high-level summary to get an immediate sense of
    the email\'s status.

-   Check DMARC Compliance: The report shows the email is DMARC
    Compliant. This is the most important overall result.

-   Check SPF Status: Both SPF Authenticated and SPF Alignment passed.
    This means the sending server was authorized.

-   Check DKIM Status: DKIM Alignment passed, but DKIM Authenticated
    failed . This is a critical finding and indicates a problem with
    the email\'s digital signature.

   <img width="1914" height="974" alt="Screenshot 2025-09-01 223613" src="https://github.com/user-attachments/assets/83da41ed-dc85-48e0-8ebd-5da534f9cde4" />


  

**Investigate the SPF Record and Email Path**

-   Next, verify why the SPF check passed.

-   Examine the SPF Record: The SPF record for the domain is v=spf1
    include:mailgun.org \~all. This record explicitly authorizes servers
    from Mailgun to send emails on its behalf.

-   Trace the Relay Information: The delivery path shows the email was
    sent from m241-136.mailgun.net.

-   Conclusion: Since the email came from a Mailgun server, which is
    authorized in the SPF record, the SPF check passed.

    <img width="1920" height="962" alt="Screenshot 2025-09-01 223652" src="https://github.com/user-attachments/assets/af03690c-31e5-44be-a165-027e5cc3c897" />


    

    

**Analyze the DKIM Failure**



<img width="1920" height="974" alt="Screenshot 2025-09-01 223706" src="https://github.com/user-attachments/assets/d4b52d29-ecf8-4cf3-be50-51c533393d94" />
