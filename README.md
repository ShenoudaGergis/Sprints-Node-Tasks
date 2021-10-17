## sprints online bank

An online banking system built with node.js & express.js

## API endpoints
1. User 
<table>
  <tr>
    <th>Endpoint</th>
    <th>Method</th>
    <th>Body</th>
  </tr>
  <tr>
    <td><code>/user/register</code></td>
    <td><code>POST</code></td>
    <td>
<pre>
 {
    "ssn"        : [number] ,
    "first_name" : [string] , 
    "last_name"  : [string] ,
    "email"      : [string] ,
    "password"   : [string] ,
    "address"    : [string] ,
    "phone"      : [number] 
 }
</pre>
  <tr>
    <td><code>/user/auth</code></td>
    <td><code>POST</code></td>
    <td>
<pre>
 {
    "email"      : [string] ,
    "password"   : [string] ,
 }
</pre>
  <tr>
    <td><code>/user/update</code></td>
    <td><code>PUT</code></td>
    <td>
<pre>
 {
    "ssn"        : [number] ,
    "first_name" : [string] , 
    "last_name"  : [string] ,
    "email"      : [string] ,
    "password"   : [string] ,
    "address"    : [string] ,
    "phone"      : [number] 
 }
</pre>
      
  <tr>
    <td><code>/user/delete</code></td>
    <td><code>DELETE</code></td>
    <td>
 <pre>
 {
    "ssn"        : [number]
 }
</pre>
    </td>
  </tr>
</table>
      
2. Account

<table>
  <tr>
    <th>Endpoint</th>
    <th>Method</th>
    <th>Body</th>
  </tr>
  <tr>
    <td><code>/account/open</code></td>
    <td><code>POST</code></td>
    <td>
<pre>
 {
    "balance"    : [number] ,
    "type"       : [string] ,
    "pin"        : [number]
 }
</pre>
  </tr>    
<tr>
    <td><code>/account/close</code></td>
    <td><code>DELETE</code></td>
    <td>
<pre>
 {
    "account_no"    : [number]
 }
</pre>
</tr>
  
  <tr>
    <td><code>/account/transaction</code></td>
    <td><code>GET</code></td>
    <td>
<pre>
 {
    "account_no"    : [number]
 }
</pre>
</tr>
  
<tr>
    <td><code>/account/withdraw</code></td>
    <td><code>POST</code></td>
    <td>
<pre>
 {
    "account_no"    : [number] ,
    "amount"        : [number] ,
 }
</pre>
<tr>
    <td><code>/account/deposite</code></td>
    <td><code>POST</code></td>
    <td>
<pre>
 {
    "account_no"    : [number] ,
    "amount"        : [number] ,
 }
</pre>
</tr> 
      
<tr>
    <td><code>/account/deposite/card</code></td>
    <td><code>POST</code></td>
    <td>
<pre>
 {
    "number"     : [number] ,
    "cvv"        : [number] ,
    "pin"        : [number] ,
    "amount"     : [number] ,
 }
</pre>
      

<tr>
    <td><code>/account/withdraw/card</code></td>
    <td><code>POST</code></td>
    <td>
<pre>
 {
    "number"     : [number] ,
    "cvv"        : [number] ,
    "pin"        : [number] ,
    "amount"     : [number] ,
 }
</pre>
</table>    
 
## Authentication
The application uses `Bearer authentication`. The token is generated by `/user/auth` call and will last for 30 mins by default
 
## Response
Each response for the listed API calls above will have `error` key, if its value is `0` that means the operation succeeded otherwise which is `1` means it's failed 
      
## How to use
For now, you can use the application locally by cloning the project in your local machine then <br />
run : `npm install` to install the required packages <br />
run : `npm start` to initialize database tables and run server<br /><br />
*The application will be hosted soon*
      
## Configurations
You can change the default configurations found in `config.js` file such as the session_timeout for each token generated in minutes
      
