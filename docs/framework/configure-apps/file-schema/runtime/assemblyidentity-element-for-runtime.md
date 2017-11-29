---
title: "&lt;assemblyIdentity&gt; elemento para &lt;tempo de execução&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/assemblyIdentity
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assemblyIdentity
helpviewer_keywords:
- <assemblyIdentity> element
- container tags, <assemblyIdentity> element
- assemblyIdentity element
ms.assetid: cea4d187-6398-4da4-af09-c1abc6a349c1
caps.latest.revision: "17"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 740b08806dff65d3ce1b8de378138c2647944fd4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="ltassemblyidentitygt-element-for-ltruntimegt"></a><span data-ttu-id="8703b-102">&lt;assemblyIdentity&gt; elemento para &lt;tempo de execução&gt;</span><span class="sxs-lookup"><span data-stu-id="8703b-102">&lt;assemblyIdentity&gt; Element for &lt;runtime&gt;</span></span>
<span data-ttu-id="8703b-103">Contém informações de identificação sobre o assembly.</span><span class="sxs-lookup"><span data-stu-id="8703b-103">Contains identifying information about the assembly.</span></span>  
  
 <span data-ttu-id="8703b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8703b-104">\<configuration></span></span>  
<span data-ttu-id="8703b-105">\<tempo de execução ></span><span class="sxs-lookup"><span data-stu-id="8703b-105">\<runtime></span></span>  
<span data-ttu-id="8703b-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="8703b-106">\<assemblyBinding></span></span>  
<span data-ttu-id="8703b-107">\<dependentAssembly ></span><span class="sxs-lookup"><span data-stu-id="8703b-107">\<dependentAssembly></span></span>  
<span data-ttu-id="8703b-108">\<assemblyIdentity ></span><span class="sxs-lookup"><span data-stu-id="8703b-108">\<assemblyIdentity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8703b-109">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8703b-109">Syntax</span></span>  
  
```xml  
   <assemblyIdentity    
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8703b-110">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="8703b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8703b-111">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="8703b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8703b-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="8703b-112">Attributes</span></span>  
  
|<span data-ttu-id="8703b-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="8703b-113">Attribute</span></span>|<span data-ttu-id="8703b-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="8703b-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="8703b-115">Atributo obrigatório.</span><span class="sxs-lookup"><span data-stu-id="8703b-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="8703b-116">O nome do assembly</span><span class="sxs-lookup"><span data-stu-id="8703b-116">The name of the assembly</span></span>|  
|`culture`|<span data-ttu-id="8703b-117">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="8703b-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="8703b-118">Uma cadeia de caracteres que especifica o idioma e país/região do assembly.</span><span class="sxs-lookup"><span data-stu-id="8703b-118">A string that specifies the language and country/region of the assembly.</span></span>|  
|`publicKeyToken`|<span data-ttu-id="8703b-119">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="8703b-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="8703b-120">Um valor hexadecimal que especifica o nome forte do assembly.</span><span class="sxs-lookup"><span data-stu-id="8703b-120">A hexadecimal value that specifies the strong name of the assembly.</span></span>|  
|`processorArchitecture`|<span data-ttu-id="8703b-121">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="8703b-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="8703b-122">Um dos valores de "x86", "amd64", "msil" ou "ia64", especificando a arquitetura do processador para um assembly que contém o código específico do processador.</span><span class="sxs-lookup"><span data-stu-id="8703b-122">One of the values "x86", "amd64", "msil", or "ia64", specifying the processor architecture for an assembly that contains processor-specific code.</span></span> <span data-ttu-id="8703b-123">Os valores não diferenciam maiusculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="8703b-123">The values are not case-sensitive.</span></span> <span data-ttu-id="8703b-124">Se o atributo é atribuído a qualquer outro valor, todo o `<assemblyIdentity>` elemento será ignorado.</span><span class="sxs-lookup"><span data-stu-id="8703b-124">If the attribute is assigned any other value, the entire `<assemblyIdentity>` element is ignored.</span></span> <span data-ttu-id="8703b-125">Consulte <xref:System.Reflection.ProcessorArchitecture>.</span><span class="sxs-lookup"><span data-stu-id="8703b-125">See <xref:System.Reflection.ProcessorArchitecture>.</span></span>|  
  
## <a name="processorarchitecture-attribute"></a><span data-ttu-id="8703b-126">processorArchitecture atributo</span><span class="sxs-lookup"><span data-stu-id="8703b-126">processorArchitecture Attribute</span></span>  
  
|<span data-ttu-id="8703b-127">Valor</span><span class="sxs-lookup"><span data-stu-id="8703b-127">Value</span></span>|<span data-ttu-id="8703b-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="8703b-128">Description</span></span>|  
|-----------|-----------------|  
|`amd64`|<span data-ttu-id="8703b-129">Apenas um processador AMD da 64 bits.</span><span class="sxs-lookup"><span data-stu-id="8703b-129">A 64-bit AMD processor only.</span></span>|  
|`ia64`|<span data-ttu-id="8703b-130">Apenas um processador da 64 bits.</span><span class="sxs-lookup"><span data-stu-id="8703b-130">A 64-bit Intel processor only.</span></span>|  
|`msil`|<span data-ttu-id="8703b-131">Neutro em relação ao processador e bits por palavra</span><span class="sxs-lookup"><span data-stu-id="8703b-131">Neutral with respect to processor and bits-per-word</span></span>|  
|`x86`|<span data-ttu-id="8703b-132">Um processador de 32 bits, ou nativo ou no Windows no ambiente do Windows (WOW) em uma plataforma de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="8703b-132">A 32-bit Intel processor, either native or in the Windows on Windows (WOW) environment on a 64-bit platform.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8703b-133">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="8703b-133">Child Elements</span></span>  
 <span data-ttu-id="8703b-134">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="8703b-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8703b-135">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="8703b-135">Parent Elements</span></span>  
  
|<span data-ttu-id="8703b-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="8703b-136">Element</span></span>|<span data-ttu-id="8703b-137">Descrição</span><span class="sxs-lookup"><span data-stu-id="8703b-137">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="8703b-138">Contém informações sobre o redirecionamento de versão e os locais dos assemblies.</span><span class="sxs-lookup"><span data-stu-id="8703b-138">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="8703b-139">O elemento raiz em cada arquivo de configuração usado pelos aplicativos do Common Language Runtime e .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8703b-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="8703b-140">Encapsula local do assembly e política de associação para cada assembly.</span><span class="sxs-lookup"><span data-stu-id="8703b-140">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="8703b-141">Use um `<dependentAssembly>` elemento para cada assembly.</span><span class="sxs-lookup"><span data-stu-id="8703b-141">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="8703b-142">Contém informações sobre associação do assembly e coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="8703b-142">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8703b-143">Comentários</span><span class="sxs-lookup"><span data-stu-id="8703b-143">Remarks</span></span>  
 <span data-ttu-id="8703b-144">Cada  **\<dependentAssembly >** elemento deve ter um  **\<assemblyIdentity >** elemento filho.</span><span class="sxs-lookup"><span data-stu-id="8703b-144">Every **\<dependentAssembly>** element must have one **\<assemblyIdentity>** child element.</span></span>  
  
 <span data-ttu-id="8703b-145">Se o `processorArchitecture` atributo estiver presente, o `<assemblyIdentity>` elemento se aplica somente ao assembly com a arquitetura de processador correspondente.</span><span class="sxs-lookup"><span data-stu-id="8703b-145">If the `processorArchitecture` attribute is present, the `<assemblyIdentity>` element applies only to the assembly with the corresponding processor architecture.</span></span> <span data-ttu-id="8703b-146">Se o `processorArchitecture` atributo não estiver presente, o `<assemblyIdentity>` elemento pode ser aplicado a um assembly com qualquer arquitetura de processador.</span><span class="sxs-lookup"><span data-stu-id="8703b-146">If the `processorArchitecture` attribute is not present, the `<assemblyIdentity>` element can apply to an assembly with any processor architecture.</span></span>  
  
 <span data-ttu-id="8703b-147">O exemplo a seguir mostra um arquivo de configuração para dois assemblies com o mesmo nome de destino diferentes duas duas arquiteturas de processador e cujas versões não tem sido mantidas em sincronia. Quando o aplicativo executa em x86 plataforma primeiro `<assemblyIdentity>` elemento se aplica e a outra é ignorada.</span><span class="sxs-lookup"><span data-stu-id="8703b-147">The following example shows a configuration file for two assemblies with the same name that target two different two processor architectures, and whose versions have not been maintained in synch. When the application executes on the x86 platform the first `<assemblyIdentity>` element applies and the other is ignored.</span></span> <span data-ttu-id="8703b-148">Se o aplicativo é executado em uma plataforma que não seja x86 ou ia64, ambos serão ignoradas.</span><span class="sxs-lookup"><span data-stu-id="8703b-148">If the application executes on a platform other than x86 or ia64, both are ignored.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"  
                  processorArchitecture="x86" />  
            <bindingRedirect oldVersion= "1.0.0.0"   
                  newVersion="1.1.0.0" />  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"   
                  processorArchitecture="ia64" />  
            <bindingRedirect oldVersion="1.0.0.0"   
                  newVersion="2.0.0.0" />  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="8703b-149">Se um arquivo de configuração contém uma `<assemblyIdentity>` elemento sem nenhum `processorArchitecture` de atributos e não contém um elemento que corresponda à plataforma, o elemento sem o `processorArchitecture` atributo será usado.</span><span class="sxs-lookup"><span data-stu-id="8703b-149">If a configuration file contains an `<assemblyIdentity>` element with no `processorArchitecture` attribute, and does not contain an element that matches the platform, the element without the `processorArchitecture` attribute is used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8703b-150">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8703b-150">Example</span></span>  
 <span data-ttu-id="8703b-151">O exemplo a seguir mostra como fornecer informações sobre um assembly.</span><span class="sxs-lookup"><span data-stu-id="8703b-151">The following example shows how to provide information about an assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for myAssembly.-->  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8703b-152">Consulte também</span><span class="sxs-lookup"><span data-stu-id="8703b-152">See Also</span></span>  
 [<span data-ttu-id="8703b-153">Esquema de configurações do tempo de execução</span><span class="sxs-lookup"><span data-stu-id="8703b-153">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="8703b-154">Esquema de arquivos de configuração</span><span class="sxs-lookup"><span data-stu-id="8703b-154">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="8703b-155">Redirecionando versões de assembly</span><span class="sxs-lookup"><span data-stu-id="8703b-155">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)