Basicaly you can mix MVC and WebForm by flagging functionality in the initialization wizard.

#Add MVC to existing WebForm Project

1) create the folder Controllers
2) create the folder Views
3) Add ref:
    3.1) System.Web.Mvc
    3.2) System.Web.Abstractions
    3.3) System.Web.Routing
    3.4) Microsoft.AspNet.WebPages (this one via nuget)

4) Add to root web.config

<system.web>

    <compilation debug="true" targetFramework="4.0">

      <assemblies>

        <add assembly="System.Web.Abstractions, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31BF3856AD364E35" />

        <add assembly="System.Web.Helpers, Version=1.0.0.0, Culture=neutral, PublicKeyToken=31BF3856AD364E35" />

        <add assembly="System.Web.Routing, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31BF3856AD364E35" />

        <add assembly="System.Web.Mvc, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31BF3856AD364E35" />

        <add assembly="System.Web.WebPages, Version=1.0.0.0, Culture=neutral, PublicKeyToken=31BF3856AD364E35" />

      </assemblies>

    </compilation>

    <pages>

      <namespaces>

        <add namespace="System.Web.Helpers" />

        <add namespace="System.Web.Mvc" />

        <add namespace="System.Web.Mvc.Ajax" />

        <add namespace="System.Web.Mvc.Html" />

        <add namespace="System.Web.Routing" />

        <add namespace="System.Web.WebPages"/>

      </namespaces>

    </pages>

 </system.web>

//Below settings to be copied outside <System.Web> and Inside <configuration>

 <runtime>

    <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">

      <dependentAssembly>

        <assemblyIdentity name="System.Web.Mvc" publicKeyToken="31bf3856ad364e35" />

        <bindingRedirect oldVersion="1.0.0.0-2.0.0.0" newVersion="3.0.0.0" />

      </dependentAssembly>

    </assemblyBinding>

  </runtime>

 5) Add a valid web.config in Views file
