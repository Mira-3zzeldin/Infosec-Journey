### 🛠️ Lab 1: Reviving a Stalled Print Queue — Print Spooler and Queue Management

**Objective:** Practice diagnosing and clearing a stuck print job, restarting the Windows Print Spooler service, and confirming printer communication with a test page — directly reinforcing this chapter's coverage of the print queue, the spooler, and Exam Objective 5.6's "multiple prints pending in queue" and "frozen print queue" symptoms.

**Environment/Tools Needed:** A Windows 10/11 PC with at least one printer installed (a physical printer, a network printer, or the built-in "Microsoft Print to PDF" virtual printer all work for this lab), and access to the Services app (no third-party software required).

**Step-by-Step Instructions:**

1. Open any document (a Notepad file is fine) and print it to your installed printer, deliberately choosing a printer that's currently offline, out of paper, or otherwise unable to complete the job — or simply queue several jobs back-to-back so at least one is still waiting.
2. Locate the printer icon in the notification area near the clock, or open Settings > Bluetooth & Devices > Printers & Scanners, select your printer, and open its queue.
3. Observe the print queue window. Record the status shown for each job (for example, Error, Printing, or Spooling).
4. Right-click the job showing an error status and select Cancel. Confirm it disappears from the queue and note whether the next job in line then begins printing automatically.
5. Now simulate a stalled spooler: open the Services app (type `services.msc` into the Windows search box and press Enter).
6. Find Print Spooler in the list. Right-click it and select Stop. Confirm its Status column no longer shows "Running."
7. With the spooler stopped, try printing another test document. Confirm that nothing happens and no icon appears in the notification area — this is the expected behavior of a stopped spooler service.
8. Right-click Print Spooler again and select Start. Confirm the Status column returns to "Running."
9. Print the same document again and confirm it now completes normally, or appears correctly in the queue.
10. Navigate to your printer's Properties (from Printers & Scanners, select the printer, then Printer Properties) and click Print Test Page on the General tab. Confirm the outcome — a successful test page, a garbled test page, or no response at all — and record which of this chapter's three explanations (connection/spooler, driver/printer fault, or printer communication working correctly) applies to your result.
11. Write two to three sentences explaining, based on this chapter, what a garbled test page would indicate that a completely blank or missing test page would not.

**Expected Result:** A cleared error job, a documented spooler stop/restart cycle showing the service's effect on print behavior, a successful print after the spooler restart, a completed (or diagnosed) test page, and a short written explanation distinguishing a driver-level fault from a connection/spooler-level fault.