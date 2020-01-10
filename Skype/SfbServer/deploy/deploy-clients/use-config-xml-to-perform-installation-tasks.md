---
title: Use config. xml para executar tarefas de instalação em clientes Skype for Business
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 'Resumo: como usar o arquivo Config.xml para especificar instruções de instalação adicionais.'
ms.openlocfilehash: d561e4f6e3213ae7dff160b9b43e02f26ecc0522
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002931"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a><span data-ttu-id="573b8-103">Use config. xml para executar tarefas de instalação em clientes Skype for Business</span><span class="sxs-lookup"><span data-stu-id="573b8-103">Use Config.xml to perform installation tasks in Skype for Business clients</span></span>

<span data-ttu-id="573b8-104">**Resumo:** como usar o arquivo Config.xml para especificar instruções de instalação adicionais.</span><span class="sxs-lookup"><span data-stu-id="573b8-104">**Summary:** How to use the Config.xml file to specify additional installation instructions.</span></span>

<span data-ttu-id="573b8-p101">Embora a Ferramenta de Personalização do Office (OCT) seja a ferramenta principal para instalação com personalização, os administradores podem usar o arquivo Config.xml para especificar instruções de instalação adicionais que não estão disponíveis na OCT. As personalizações a seguir só podem ser feitas usando o arquivo Config.xml:</span><span class="sxs-lookup"><span data-stu-id="573b8-p101">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT. The following customizations can only be made by using the Config.xml file:</span></span>

- <span data-ttu-id="573b8-107">Especificar o caminho do ponto de instalação de rede.</span><span class="sxs-lookup"><span data-stu-id="573b8-107">Specify the path of the network installation point.</span></span>

- <span data-ttu-id="573b8-108">Selecionar os produtos a serem instalados.</span><span class="sxs-lookup"><span data-stu-id="573b8-108">Select the products to install.</span></span>

- <span data-ttu-id="573b8-109">Configure o registro em log e o local do arquivo de personalização da Instalação e atualizações de software.</span><span class="sxs-lookup"><span data-stu-id="573b8-109">Configure logging and the location of the Setup customization file and software updates.</span></span>

- <span data-ttu-id="573b8-110">Especifique as opções de instalação, como nome do usuário.</span><span class="sxs-lookup"><span data-stu-id="573b8-110">Specify installation options, such as user name.</span></span>

- <span data-ttu-id="573b8-111">Copiar a LIS (origem de instalação local) no computador do usuário, mas sem instalar o Office.</span><span class="sxs-lookup"><span data-stu-id="573b8-111">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>

- <span data-ttu-id="573b8-112">Adicionar ou remover idiomas da instalação.</span><span class="sxs-lookup"><span data-stu-id="573b8-112">Add or remove languages from the installation.</span></span>

<span data-ttu-id="573b8-113">Recomendamos que você use o arquivo config. xml para configurar a instalação silenciosa do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="573b8-113">We recommend that you use the Config.xml file to configure Skype for Business silent installation.</span></span> 

<span data-ttu-id="573b8-114">Por padrão, o arquivo config. xml armazenado na pasta principal do produto (por exemplo, \ _produto_. WW) instrui a instalação a instalar esse produto.</span><span class="sxs-lookup"><span data-stu-id="573b8-114">By default, the Config.xml file that is stored in the core product folder (for example, \ _product_.WW) directs Setup to install that product.</span></span> <span data-ttu-id="573b8-115">Por exemplo, o arquivo config. xml na seguinte pasta instala o Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="573b8-115">For example, the Config.xml file in the following folder installs Skype for Business:</span></span>

- <span data-ttu-id="573b8-116">\\server\share\Skype15\Skype.WW \Config.xml</span><span class="sxs-lookup"><span data-stu-id="573b8-116">\\server\share\Skype15\Skype.WW \Config.xml</span></span>

<span data-ttu-id="573b8-117">Os elementos config. xml mais comumente usados para a instalação do Skype for Business estão listados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="573b8-117">The Config.xml elements most commonly used for Skype for Business installation are listed in the following table.</span></span>

<span data-ttu-id="573b8-118">**Elementos de Config.xml**</span><span class="sxs-lookup"><span data-stu-id="573b8-118">**Config.xml elements**</span></span>


| <span data-ttu-id="573b8-119">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="573b8-119">**Element**</span></span>              | <span data-ttu-id="573b8-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="573b8-120">**Description**</span></span>                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="573b8-121">Configuração</span><span class="sxs-lookup"><span data-stu-id="573b8-121">Configuration</span></span>  <br/>     | <span data-ttu-id="573b8-p103">Elemento de nível superior (obrigatório). Contém o atributo Product, por exemplo: Product=Lync (funcionará para clientes do Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="573b8-p103">Top-level element (required). Contains the Product attribute, for example: Product=Lync (This will work for Skype for Business clients)</span></span>  <br/>                                                                                                                                                          |
| <span data-ttu-id="573b8-124">OptionState</span><span class="sxs-lookup"><span data-stu-id="573b8-124">OptionState</span></span>  <br/>       | <span data-ttu-id="573b8-125">Especifica como os recursos específicos de produto são manipulados durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="573b8-125">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="573b8-126">Use os atributos a seguir para impedir a instalação de serviços corporativos de conectividade, que incluem componentes compartilhados que interferem no Outlook:</span><span class="sxs-lookup"><span data-stu-id="573b8-126">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook:</span></span> <br/>  <span data-ttu-id="573b8-127">Id="LOBiMain"</span><span class="sxs-lookup"><span data-stu-id="573b8-127">Id="LOBiMain"</span></span> <br/>  <span data-ttu-id="573b8-128">State="Absent"</span><span class="sxs-lookup"><span data-stu-id="573b8-128">State="Absent"</span></span> <br/>  <span data-ttu-id="573b8-129">Children="Force"</span><span class="sxs-lookup"><span data-stu-id="573b8-129">Children="Force"</span></span> <br/> |
| <span data-ttu-id="573b8-130">Exibir</span><span class="sxs-lookup"><span data-stu-id="573b8-130">Display</span></span>  <br/>           | <span data-ttu-id="573b8-p105">O nível deUI que a Instalação exibe para o usuário. Entre os atributos comuns estão os seguintes:</span><span class="sxs-lookup"><span data-stu-id="573b8-p105">The level of UI that Setup displays to the user. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="573b8-133">CompletionNotice = "Sim"</span><span class="sxs-lookup"><span data-stu-id="573b8-133">CompletionNotice="Yes"</span></span>                                                                                                                                                                                |
| <span data-ttu-id="573b8-134">Registro em log</span><span class="sxs-lookup"><span data-stu-id="573b8-134">Logging</span></span>  <br/>           | <span data-ttu-id="573b8-p106">Opções para o tipo de registro em log executado pela Instalação. Entre os atributos comuns estão os seguintes:</span><span class="sxs-lookup"><span data-stu-id="573b8-p106">Options for the kind of logging that Setup performs. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="573b8-137">Digite = "desativado"</span><span class="sxs-lookup"><span data-stu-id="573b8-137">Type ="Off"</span></span>                                                                                                                                                                                       |
| <span data-ttu-id="573b8-138">Configuração</span><span class="sxs-lookup"><span data-stu-id="573b8-138">Setting</span></span>  <br/>           | <span data-ttu-id="573b8-p107">Especifica valores para as propriedades do Windows Installer. Entre os atributos comuns estão os seguintes:</span><span class="sxs-lookup"><span data-stu-id="573b8-p107">Specifies values for Windows Installer properties. Typical attributes include the following: </span></span><br/>  <span data-ttu-id="573b8-141">Setting ID = " *Name*" (o nome da Propriedade do Windows Installer)</span><span class="sxs-lookup"><span data-stu-id="573b8-141">Setting Id=" *name*" (the name of the Windows Installer property)</span></span>  <br/>  <span data-ttu-id="573b8-142">Valor = " *valor*" (o valor a ser atribuído à propriedade)</span><span class="sxs-lookup"><span data-stu-id="573b8-142">Value=" *value*" (the value to assign to the property)</span></span>  <br/>                                                             |
| <span data-ttu-id="573b8-143">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="573b8-143">DistributionPoint</span></span>  <br/> | <span data-ttu-id="573b8-p108">O caminho totalmente qualificado do ponto de instalação de rede do qual a instalação deve ser executada. Inclui o atributo Location:</span><span class="sxs-lookup"><span data-stu-id="573b8-p108">The fully qualified path of the network installation point from which the installation is to run. Includes the Location attribute: </span></span><br/>  <span data-ttu-id="573b8-146">Location = " *caminho*"</span><span class="sxs-lookup"><span data-stu-id="573b8-146">Location=" *path*"</span></span>  <br/>                                                                                                                                     |

<span data-ttu-id="573b8-147">O exemplo a seguir mostra um arquivo config. xml para uma instalação silenciosa típica do cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="573b8-147">The following example shows a Config.xml file for a typical silent installation of the Skype for Business client.</span></span> 

```xml
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

<span data-ttu-id="573b8-148">Informações detalhadas sobre como usar o arquivo config. xml para executar tarefas de instalação e manutenção do Office [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514)estão disponíveis em.</span><span class="sxs-lookup"><span data-stu-id="573b8-148">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).</span></span>

## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="573b8-149">Para personalizar o arquivo Config.xml</span><span class="sxs-lookup"><span data-stu-id="573b8-149">To customize the Config.xml file</span></span>

1. <span data-ttu-id="573b8-150">Abra o arquivo Config.xml usando uma ferramenta editora de texto, como o Bloco de Notas.</span><span class="sxs-lookup"><span data-stu-id="573b8-150">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>

2. <span data-ttu-id="573b8-151">Localize as linhas que contêm os elementos que você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="573b8-151">Locate the lines that contain the elements you want to change.</span></span>

3. <span data-ttu-id="573b8-152">Modifique a entrada do elemento com as opções silenciosas que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="573b8-152">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="573b8-153">Certifique-se de remover os delimitadores de comentário "\<!--" e "--\>".</span><span class="sxs-lookup"><span data-stu-id="573b8-153">Make sure that you remove the comment delimiters, "\<!--" and "--\>".</span></span> <span data-ttu-id="573b8-154">Por exemplo, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="573b8-154">For example, use the following syntax:</span></span>

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. <span data-ttu-id="573b8-155">Salve o arquivo Config.xml.</span><span class="sxs-lookup"><span data-stu-id="573b8-155">Save the Config.xml file.</span></span>


