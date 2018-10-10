# iis-rules

Common IIS Rules

Url Rewrite rule: remove WWW from all urls of a website without hard coding the domain in the rule - uses Regex.

```
 <rewrite>       
         <rules>
            <rule name="Remove WWW" enabled="true" stopProcessing="true">
             <match url="(.*)" />
             <conditions logicalGrouping="MatchAny">
                  <add input="{HTTP_HOST}" pattern="^(www\.)(.*)$" />
             </conditions>
             <action type="Redirect" url="https://{C:2}/{R:1}" redirectType="Permanent" appendQueryString="true" />
            </rule>
	</rules>
   </rewrite>
 ```
        
