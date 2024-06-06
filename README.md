# Automated-multi-currency-invoicing
This project is an automated system designed to handle multi-currency invoicing and posting between two systems: a non-multi-currency BPO system and Sage Pastel, which supports multi-currency transactions. The system ensures that all invoices are correctly processed and posted with the appropriate currency conversion applied.

## Features
<ul>
  <li>
    <b>Automated Invoice Processing:</b> Continuously checks for new invoices in the BPO system and processes them automatically.
  </li>
  <li>
    <b>Currency Conversion:</b> Converts USD invoices to ZWL using the daily exchange rate provided by Sage Pastel.
  </li>
  <li>
    <b>Database Integration:</b> Seamlessly integrates with both BPO and Sage Pastel databases.
  </li>
  <li>
    <b>Error Handling:</b> Skips invoices when the exchange rate is unavailable and logs such instances for review.
  </li>
  <li>
    <b>Scheduled Execution:</b> Utilizes task scheduling to run the processing script at regular intervals without manual intervention.
  </li>
</ul>

## Technical Details
<ul>
  <li>
    <b>Backend Framework:</b> Django
  </li>
  <li>
    <b>Database:</b> SQL Server (BPO and Sage Pastel databases)
  </li>
  <li>
    <b>Programming Language:</b> Python
  </li>
  <li>
    <b>Dependencies:</b> 'pyodbc' for database connections, schedule for task scheduling
  </li>
</ul>

## How It Works
<ul>
  <li>
    <b>Fetch New Invoices:</b> The system fetches new invoices from the BPO system that are marked as unprocessed.
  </li>
  <li>
    <b>Currency Check and Conversion:</b> It checks the currency of each invoice. If the currency is USD, it fetches the exchange rate from Sage Pastel and converts the amount to ZWL.
  </li>
  <li>
    <b>Posting Invoices:</b> The converted invoices (or ZWL invoices without conversion) are posted to Sage Pastel.
  </li>
  <li>
    <b>Marking Processed Invoices:</b> Invoices that are successfully posted are marked as processed in the BPO system.
  </li>
</ul>
