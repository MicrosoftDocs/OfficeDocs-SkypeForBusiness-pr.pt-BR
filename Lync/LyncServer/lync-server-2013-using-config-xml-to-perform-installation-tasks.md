---
title: 'Lync Server 2013: usando o config. xml para executar tarefas de instalação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Config.xml to perform installation tasks
ms:assetid: 0813184a-ab40-417c-b3a3-c2090766b831
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204651(v=OCS.15)
ms:contentKeyID: 48183332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b6b06b270157bc1aa2387662229dbff3eb8f4d5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138712"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-configxml-to-perform-installation-tasks-in-lync-server-2013"></a><span data-ttu-id="5982d-102">Usando o config. xml para executar tarefas de instalação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5982d-102">Using Config.xml to perform installation tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5982d-103">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="5982d-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="5982d-p101">Embora a Ferramenta de Personalização do Office (OCT) seja a ferramenta principal para instalação com personalização, os administradores podem usar o arquivo Config.xml para especificar instruções de instalação adicionais que não estão disponíveis na OCT. As personalizações a seguir só podem ser feitas usando o arquivo Config.xml:</span><span class="sxs-lookup"><span data-stu-id="5982d-p101">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT. The following customizations can only be made by using the Config.xml file:</span></span>

  - <span data-ttu-id="5982d-106">Especificar o caminho do ponto de instalação de rede.</span><span class="sxs-lookup"><span data-stu-id="5982d-106">Specify the path of the network installation point.</span></span>

  - <span data-ttu-id="5982d-107">Selecionar os produtos a serem instalados.</span><span class="sxs-lookup"><span data-stu-id="5982d-107">Select the products to install.</span></span>

  - <span data-ttu-id="5982d-108">Configure o registro em log e o local do arquivo de personalização da Instalação e atualizações de software.</span><span class="sxs-lookup"><span data-stu-id="5982d-108">Configure logging and the location of the Setup customization file and software updates.</span></span>

  - <span data-ttu-id="5982d-109">Especifique as opções de instalação, como nome do usuário.</span><span class="sxs-lookup"><span data-stu-id="5982d-109">Specify installation options, such as user name.</span></span>

  - <span data-ttu-id="5982d-110">Copiar a LIS (origem de instalação local) no computador do usuário, mas sem instalar o Office.</span><span class="sxs-lookup"><span data-stu-id="5982d-110">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>

  - <span data-ttu-id="5982d-111">Adicionar ou remover idiomas da instalação.</span><span class="sxs-lookup"><span data-stu-id="5982d-111">Add or remove languages from the installation.</span></span>

<span data-ttu-id="5982d-112">Recomendamos que você use o arquivo config. xml para configurar a instalação silenciosa do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="5982d-112">We recommend that you use the Config.xml file to configure Lync 2013 silent installation.</span></span>

<span data-ttu-id="5982d-113">Por padrão, o arquivo config. xml armazenado na pasta principal do produto (por exemplo, \\produto. WW) direciona a instalação para instalar o produto.</span><span class="sxs-lookup"><span data-stu-id="5982d-113">By default, the Config.xml file that is stored in the core product folder (for example, \\product.WW) directs Setup to install that product.</span></span> <span data-ttu-id="5982d-114">Por exemplo, o arquivo config. xml na pasta a seguir instala o Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="5982d-114">For example, the Config.xml file in the following folder installs Lync 2013:</span></span>

  - <span data-ttu-id="5982d-115">\\\\Server\\share\\Lync15\\Lync. WW \\config. xml</span><span class="sxs-lookup"><span data-stu-id="5982d-115">\\\\server\\share\\Lync15\\Lync.WW \\Config.xml</span></span>

<span data-ttu-id="5982d-116">Os elementos config. XML usados com mais frequência para a instalação do Lync 2013 estão listados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="5982d-116">The Config.xml elements most commonly used for Lync 2013 installation are listed in the following table.</span></span>

### <a name="configxml-elements"></a><span data-ttu-id="5982d-117">Elementos de Config.xml</span><span class="sxs-lookup"><span data-stu-id="5982d-117">Config.xml elements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5982d-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="5982d-118">Element</span></span></th>
<th><span data-ttu-id="5982d-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="5982d-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5982d-120">Configuração</span><span class="sxs-lookup"><span data-stu-id="5982d-120">Configuration</span></span></p></td>
<td><p><span data-ttu-id="5982d-p103">Elemento de nível superior (obrigatório). Contém o atributo Product, por exemplo: Product=Lync</span><span class="sxs-lookup"><span data-stu-id="5982d-p103">Top-level element (required). Contains the Product attribute, for example: Product=Lync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5982d-123">OptionState</span><span class="sxs-lookup"><span data-stu-id="5982d-123">OptionState</span></span></p></td>
<td><p><span data-ttu-id="5982d-124">Especifica como os recusos de produto específicos são manipulados durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="5982d-124">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="5982d-125">Use os seguintes atributos para impedir a instalação dos serviços corporativos de conectividade, que incluem componentes compartilhados que interferem no Outlook 2010:</span><span class="sxs-lookup"><span data-stu-id="5982d-125">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook 2010:</span></span></p>
<ul>
<li><p><span data-ttu-id="5982d-126">ID =&quot;LOBiMain&quot;</span><span class="sxs-lookup"><span data-stu-id="5982d-126">Id=&quot;LOBiMain&quot;</span></span></p></li>
<li><p><span data-ttu-id="5982d-127">Estado =&quot;ausente&quot;</span><span class="sxs-lookup"><span data-stu-id="5982d-127">State=&quot;Absent&quot;</span></span></p></li>
<li><p><span data-ttu-id="5982d-128">Children =&quot;Force&quot;</span><span class="sxs-lookup"><span data-stu-id="5982d-128">Children=&quot;Force&quot;</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5982d-129">Exibir</span><span class="sxs-lookup"><span data-stu-id="5982d-129">Display</span></span></p></td>
<td><p><span data-ttu-id="5982d-p105">O nível deUI que a Instalação exibe para o usuário. Entre os atributos comuns estão os seguintes:</span><span class="sxs-lookup"><span data-stu-id="5982d-p105">The level of UI that Setup displays to the user. Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="5982d-132">CompletionNotice =&quot;sim&quot; | &quot;não&quot;(padrão)</span><span class="sxs-lookup"><span data-stu-id="5982d-132">CompletionNotice=&quot;Yes&quot; | &quot;No&quot;(default)</span></span></p></li>
<li><p><span data-ttu-id="5982d-133">AcceptEula =&quot;sim&quot; | &quot;não&quot;(padrão)</span><span class="sxs-lookup"><span data-stu-id="5982d-133">AcceptEula=&quot;Yes&quot; | &quot;No&quot;(default)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5982d-134">Registro em log</span><span class="sxs-lookup"><span data-stu-id="5982d-134">Logging</span></span></p></td>
<td><p><span data-ttu-id="5982d-p106">Opções para o tipo de registro em log executado pela Instalação. Entre os atributos comuns estão os seguintes:</span><span class="sxs-lookup"><span data-stu-id="5982d-p106">Options for the kind of logging that Setup performs. Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="5982d-137">Digite =&quot;off&quot; | &quot;Standard&quot;(padrão) | &quot;Detalhado&quot;</span><span class="sxs-lookup"><span data-stu-id="5982d-137">Type =&quot;Off&quot; | &quot;Standard&quot;(default) | &quot;Verbose&quot;</span></span></p></li>
<li><p><span data-ttu-id="5982d-138">Template=”filename.txt” (o nome do arquivo de log)</span><span class="sxs-lookup"><span data-stu-id="5982d-138">Template=”filename.txt” (the name of the log file)</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5982d-139">Configuração</span><span class="sxs-lookup"><span data-stu-id="5982d-139">Setting</span></span></p></td>
<td><p><span data-ttu-id="5982d-p107">Especifica valores para as propriedades do Windows Installer. Entre os atributos comuns estão os seguintes:</span><span class="sxs-lookup"><span data-stu-id="5982d-p107">Specifies values for Windows Installer properties. Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="5982d-142">ID da configuração&quot;=&quot; nome (o nome da Propriedade do Windows Installer)</span><span class="sxs-lookup"><span data-stu-id="5982d-142">Setting Id=&quot;name&quot; (the name of the Windows Installer property)</span></span></p></li>
<li><p><span data-ttu-id="5982d-143">Valor =&quot;valor&quot; (o valor a ser atribuído à propriedade)</span><span class="sxs-lookup"><span data-stu-id="5982d-143">Value=&quot;value&quot; (the value to assign to the property)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5982d-144">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="5982d-144">DistributionPoint</span></span></p></td>
<td><p><span data-ttu-id="5982d-p108">O caminho totalmente qualificado do ponto de instalação de rede do qual a instalação deve ser executada. Inclui o atributo Location:</span><span class="sxs-lookup"><span data-stu-id="5982d-p108">The fully qualified path of the network installation point from which the installation is to run. Includes the Location attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="5982d-147">Location = "caminho"</span><span class="sxs-lookup"><span data-stu-id="5982d-147">Location=”path”</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5982d-148">O exemplo a seguir mostra um arquivo config. xml para uma instalação silenciosa típica do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="5982d-148">The following example shows a Config.xml file for a typical silent installation of Lync 2013.</span></span>

    <Configuration Product="Lync">
      <OptionState Id="LOBiMain" State="Absent" Children="Force" />
      <Display Level="None" CompletionNotice="No" AcceptEula="Yes" />
      <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
      <Setting Id="SETUP_REBOOT" Value="Never" />
      <DistributionPoint Location="\\server\share\Lync15" />
    </Configuration>

<span data-ttu-id="5982d-149">Informações detalhadas sobre como usar o arquivo config. xml para executar tarefas de instalação e manutenção do Office <https://go.microsoft.com/fwlink/p/?linkid=267514>estão disponíveis em.</span><span class="sxs-lookup"><span data-stu-id="5982d-149">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at <https://go.microsoft.com/fwlink/p/?linkid=267514>.</span></span>

<div>

## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="5982d-150">Para personalizar o arquivo Config.xml</span><span class="sxs-lookup"><span data-stu-id="5982d-150">To customize the Config.xml file</span></span>

1.  <span data-ttu-id="5982d-151">Abra o arquivo Config.xml usando uma ferramenta editora de texto, como o Bloco de Notas.</span><span class="sxs-lookup"><span data-stu-id="5982d-151">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>

2.  <span data-ttu-id="5982d-152">Localize as linhas que contêm os elementos que você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="5982d-152">Locate the lines that contain the elements you want to change.</span></span>

3.  <span data-ttu-id="5982d-153">Modifique a entrada do elemento com as opções silenciosas que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="5982d-153">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="5982d-154">Certifique-se de remover os delimitadores de comentário,\<\!"--" e "-\>-".</span><span class="sxs-lookup"><span data-stu-id="5982d-154">Make sure that you remove the comment delimiters, "\<\!--" and "--\>".</span></span> <span data-ttu-id="5982d-155">Por exemplo, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="5982d-155">For example, use the following syntax:</span></span>
    
        < DistributionPoint Location="\\server\share\Lync15" />

4.  <span data-ttu-id="5982d-156">Salve o arquivo Config.xml.</span><span class="sxs-lookup"><span data-stu-id="5982d-156">Save the Config.xml file.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

