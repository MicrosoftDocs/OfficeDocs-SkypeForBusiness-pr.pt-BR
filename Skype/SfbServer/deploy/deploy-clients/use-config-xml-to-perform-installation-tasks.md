---
title: Usar o config. XML para executar tarefas de instalação no Skype para clientes corporativos
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 'Resumo: como usar o arquivo Config.xml para especificar instruções de instalação adicionais.'
ms.openlocfilehash: ea869fe2b49d5c1a5b4e04c3bc75cfd52b66555e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21003505"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a><span data-ttu-id="6e754-103">Usar o config. XML para executar tarefas de instalação no Skype para clientes corporativos</span><span class="sxs-lookup"><span data-stu-id="6e754-103">Use Config.xml to perform installation tasks in Skype for Business clients</span></span>
 
<span data-ttu-id="6e754-104">**Resumo:** como usar o arquivo Config.xml para especificar instruções de instalação adicionais.</span><span class="sxs-lookup"><span data-stu-id="6e754-104">**Summary:** How to use the Config.xml file to specify additional installation instructions.</span></span>
  
<span data-ttu-id="6e754-p101">Embora a Ferramenta de Personalização do Office (OCT) seja a ferramenta principal para instalação com personalização, os administradores podem usar o arquivo Config.xml para especificar instruções de instalação adicionais que não estão disponíveis na OCT. As personalizações a seguir só podem ser feitas usando o arquivo Config.xml:</span><span class="sxs-lookup"><span data-stu-id="6e754-p101">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT. The following customizations can only be made by using the Config.xml file:</span></span>
  
- <span data-ttu-id="6e754-107">Especificar o caminho do ponto de instalação de rede.</span><span class="sxs-lookup"><span data-stu-id="6e754-107">Specify the path of the network installation point.</span></span>
    
- <span data-ttu-id="6e754-108">Selecionar os produtos a serem instalados.</span><span class="sxs-lookup"><span data-stu-id="6e754-108">Select the products to install.</span></span>
    
- <span data-ttu-id="6e754-109">Configure o registro em log e o local do arquivo de personalização da Instalação e atualizações de software.</span><span class="sxs-lookup"><span data-stu-id="6e754-109">Configure logging and the location of the Setup customization file and software updates.</span></span>
    
- <span data-ttu-id="6e754-110">Especifique as opções de instalação, como nome do usuário.</span><span class="sxs-lookup"><span data-stu-id="6e754-110">Specify installation options, such as user name.</span></span>
    
- <span data-ttu-id="6e754-111">Copiar a LIS (origem de instalação local) no computador do usuário, mas sem instalar o Office.</span><span class="sxs-lookup"><span data-stu-id="6e754-111">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>
    
- <span data-ttu-id="6e754-112">Adicionar ou remover idiomas da instalação.</span><span class="sxs-lookup"><span data-stu-id="6e754-112">Add or remove languages from the installation.</span></span>
    
<span data-ttu-id="6e754-113">Recomendamos que você use o arquivo config. XML para configurar o Skype para instalação silenciosa de negócios.</span><span class="sxs-lookup"><span data-stu-id="6e754-113">We recommend that you use the Config.xml file to configure Skype for Business silent installation.</span></span> 
  
<span data-ttu-id="6e754-114">Por padrão, o arquivo config. XML que é armazenado na pasta principal do produto (por exemplo, \ _produto_. WW) direciona a instalação para instalar o produto.</span><span class="sxs-lookup"><span data-stu-id="6e754-114">By default, the Config.xml file that is stored in the core product folder (for example, \ _product_.WW) directs Setup to install that product.</span></span> <span data-ttu-id="6e754-115">Por exemplo, o arquivo config. XML na pasta a seguir instala Skype para negócios:</span><span class="sxs-lookup"><span data-stu-id="6e754-115">For example, the Config.xml file in the following folder installs Skype for Business:</span></span>
  
- <span data-ttu-id="6e754-116">\\server\share\Skype15\Skype.WW \Config.xml</span><span class="sxs-lookup"><span data-stu-id="6e754-116">\\server\share\Skype15\Skype.WW \Config.xml</span></span>
    
<span data-ttu-id="6e754-117">Os elementos do config. XML mais comuns utilizados para Skype para instalação de negócios são listados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="6e754-117">The Config.xml elements most commonly used for Skype for Business installation are listed in the following table.</span></span>
  
<span data-ttu-id="6e754-118">**Elementos de Config.xml**</span><span class="sxs-lookup"><span data-stu-id="6e754-118">**Config.xml elements**</span></span>

|<span data-ttu-id="6e754-119">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="6e754-119">**Element**</span></span>|<span data-ttu-id="6e754-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="6e754-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6e754-121">Configuração</span><span class="sxs-lookup"><span data-stu-id="6e754-121">Configuration</span></span>  <br/> |<span data-ttu-id="6e754-p103">Elemento de nível superior (obrigatório). Contém o atributo Product, por exemplo: Product=Lync (funcionará para clientes do Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="6e754-p103">Top-level element (required). Contains the Product attribute, for example: Product=Lync (This will work for Skype for Business clients)</span></span>  <br/> |
|<span data-ttu-id="6e754-124">OptionState</span><span class="sxs-lookup"><span data-stu-id="6e754-124">OptionState</span></span>  <br/> | <span data-ttu-id="6e754-125">Especifica como os recursos específicos de produto são manipulados durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="6e754-125">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="6e754-126">Use os seguintes atributos para evitar a instalação dos serviços corporativos de conectividade, que inclui os componentes compartilhados que interferem no Outlook:</span><span class="sxs-lookup"><span data-stu-id="6e754-126">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook:</span></span> <br/>  <span data-ttu-id="6e754-127">ID = "LOBiMain"</span><span class="sxs-lookup"><span data-stu-id="6e754-127">Id="LOBiMain"</span></span> <br/>  <span data-ttu-id="6e754-128">State="Absent"</span><span class="sxs-lookup"><span data-stu-id="6e754-128">State="Absent"</span></span> <br/>  <span data-ttu-id="6e754-129">Children="Force"</span><span class="sxs-lookup"><span data-stu-id="6e754-129">Children="Force"</span></span> <br/> |
|<span data-ttu-id="6e754-130">Exibir</span><span class="sxs-lookup"><span data-stu-id="6e754-130">Display</span></span>  <br/> | <span data-ttu-id="6e754-p105">O nível deUI que a Instalação exibe para o usuário. Entre os atributos comuns estão os seguintes:</span><span class="sxs-lookup"><span data-stu-id="6e754-p105">The level of UI that Setup displays to the user. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="6e754-133">CompletionNotice = "Yes"</span><span class="sxs-lookup"><span data-stu-id="6e754-133">CompletionNotice="Yes"</span></span> | <span data-ttu-id="6e754-134">"No"(default)</span><span class="sxs-lookup"><span data-stu-id="6e754-134">"No"(default)</span></span> <br/>  <span data-ttu-id="6e754-135">AcceptEula = "Yes"</span><span class="sxs-lookup"><span data-stu-id="6e754-135">AcceptEula="Yes"</span></span> | <span data-ttu-id="6e754-136">"No"(default)</span><span class="sxs-lookup"><span data-stu-id="6e754-136">"No"(default)</span></span> <br/> |
|<span data-ttu-id="6e754-137">Registro em log</span><span class="sxs-lookup"><span data-stu-id="6e754-137">Logging</span></span>  <br/> | <span data-ttu-id="6e754-p106">Opções para o tipo de registro em log executado pela Instalação. Entre os atributos comuns estão os seguintes:</span><span class="sxs-lookup"><span data-stu-id="6e754-p106">Options for the kind of logging that Setup performs. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="6e754-140">Tipo = "Off"</span><span class="sxs-lookup"><span data-stu-id="6e754-140">Type ="Off"</span></span> | <span data-ttu-id="6e754-141">"Standard</span><span class="sxs-lookup"><span data-stu-id="6e754-141">"Standard"(default)</span></span> | <span data-ttu-id="6e754-142">"Verbose"</span><span class="sxs-lookup"><span data-stu-id="6e754-142">"Verbose"</span></span> <br/>  <span data-ttu-id="6e754-143">Modelo = " _filename_txt" (o nome do arquivo de log)</span><span class="sxs-lookup"><span data-stu-id="6e754-143">Template=" _filename_.txt" (the name of the log file)</span></span>  <br/> |
|<span data-ttu-id="6e754-144">Configuração</span><span class="sxs-lookup"><span data-stu-id="6e754-144">Setting</span></span>  <br/> | <span data-ttu-id="6e754-p107">Especifica valores para as propriedades do Windows Installer. Entre os atributos comuns estão os seguintes:</span><span class="sxs-lookup"><span data-stu-id="6e754-p107">Specifies values for Windows Installer properties. Typical attributes include the following: </span></span><br/>  <span data-ttu-id="6e754-147">Setting Id = " _nome_" (o nome da propriedade do Windows Installer)</span><span class="sxs-lookup"><span data-stu-id="6e754-147">Setting Id=" _name_" (the name of the Windows Installer property)</span></span>  <br/>  <span data-ttu-id="6e754-148">Valor = " _valor_" (o valor a ser atribuído à propriedade)</span><span class="sxs-lookup"><span data-stu-id="6e754-148">Value=" _value_" (the value to assign to the property)</span></span>  <br/> |
|<span data-ttu-id="6e754-149">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="6e754-149">DistributionPoint</span></span>  <br/> | <span data-ttu-id="6e754-p108">O caminho totalmente qualificado do ponto de instalação de rede do qual a instalação deve ser executada. Inclui o atributo Location:</span><span class="sxs-lookup"><span data-stu-id="6e754-p108">The fully qualified path of the network installation point from which the installation is to run. Includes the Location attribute: </span></span><br/>  <span data-ttu-id="6e754-152">Local = " _caminho_"</span><span class="sxs-lookup"><span data-stu-id="6e754-152">Location=" _path_"</span></span>  <br/> |
   
<span data-ttu-id="6e754-153">O exemplo a seguir mostra um arquivo config. XML para uma instalação silenciosa típica do Skype para o cliente de negócios.</span><span class="sxs-lookup"><span data-stu-id="6e754-153">The following example shows a Config.xml file for a typical silent installation of the Skype for Business client.</span></span> 
  
```
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

<span data-ttu-id="6e754-154">Informações detalhadas sobre como usar o arquivo config. XML para executar tarefas de instalação e manutenção do Office estão disponíveis em [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).</span><span class="sxs-lookup"><span data-stu-id="6e754-154">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).</span></span>
  
## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="6e754-155">Para personalizar o arquivo Config.xml</span><span class="sxs-lookup"><span data-stu-id="6e754-155">To customize the Config.xml file</span></span>

1. <span data-ttu-id="6e754-156">Abra o arquivo Config.xml usando uma ferramenta editora de texto, como o Bloco de Notas.</span><span class="sxs-lookup"><span data-stu-id="6e754-156">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>
    
2. <span data-ttu-id="6e754-157">Localize as linhas que contêm os elementos que você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="6e754-157">Locate the lines that contain the elements you want to change.</span></span>
    
3. <span data-ttu-id="6e754-158">Modifique a entrada do elemento com as opções silenciosas que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="6e754-158">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="6e754-159">Certifique-se de que você remova os delimitadores de comentário, "\<! –" e "–\>".</span><span class="sxs-lookup"><span data-stu-id="6e754-159">Make sure that you remove the comment delimiters, "\<!--" and "--\>".</span></span> <span data-ttu-id="6e754-160">Por exemplo, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="6e754-160">For example, use the following syntax:</span></span>
    
  <pre>
  < DistributionPoint Location="\\server\share\Skype15" />
  </pre>

4. <span data-ttu-id="6e754-161">Salve o arquivo Config.xml.</span><span class="sxs-lookup"><span data-stu-id="6e754-161">Save the Config.xml file.</span></span>
    

