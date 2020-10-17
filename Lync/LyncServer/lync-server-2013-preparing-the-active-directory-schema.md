---
title: 'Lync Server 2013: preparando o esquema do Active Directory'
description: 'Lync Server 2013: preparando o esquema do Active Directory.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the Active Directory schema
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398119(v=OCS.15)
ms:contentKeyID: 48183300
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3df7533dcbabe278fd366b441cfd8daa83f54b23
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560307"
---
# <a name="preparing-the-active-directory-schema-in-lync-server-2013"></a><span data-ttu-id="2daac-103">Preparando o esquema do Active Directory no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2daac-103">Preparing the Active Directory schema in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2daac-104">_**Última modificação do tópico:** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="2daac-104">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="2daac-105">Antes de começar a preparar os serviços de domínio do Active Directory, você pode abrir os arquivos de esquema usando um editor de texto, como o bloco de notas do Windows, ou ver [extensões, classes e atributos de esquema do Active Directory usados pelo Lync server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) para examinar todas as extensões de esquema de serviços de domínio do Active Directory que serão modificadas para o lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2daac-105">Before you begin preparing Active Directory Domain Services, you can open the schema files by using a text editor, such as Windows Notepad, or see [Active Directory schema extensions, classes, and attributes used by Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) to review all the Active Directory Domain Services schema extensions that will be modified for Lync Server 2013.</span></span> <span data-ttu-id="2daac-106">O Lync Server usa quatro arquivos de esquema:</span><span class="sxs-lookup"><span data-stu-id="2daac-106">Lync Server uses four schema files:</span></span>

  - <span data-ttu-id="2daac-107">ExternalSchema. ldf, que é usado para interoperabilidade com o Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="2daac-107">ExternalSchema.ldf, which is used for interoperability with Microsoft Exchange Server</span></span>

  - <span data-ttu-id="2daac-108">ServerSchema. ldf, que é o arquivo de esquema principal do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2daac-108">ServerSchema.ldf, which is the primary Lync Server 2013 schema file</span></span>

  - <span data-ttu-id="2daac-109">BackCompatSchema.ldf, que é usado para a interoperabilidade com quaisquer componentes de versões anteriores</span><span class="sxs-lookup"><span data-stu-id="2daac-109">BackCompatSchema.ldf, which is used for interoperability with any components from prior releases</span></span>

  - <span data-ttu-id="2daac-110">VersionSchema.ldf, que é usado para informações sobre a versão do esquema preparado</span><span class="sxs-lookup"><span data-stu-id="2daac-110">VersionSchema.ldf, which is used for version information of the prepared schema</span></span>

<span data-ttu-id="2daac-111">Todos os arquivos .ldf são instalados durante a preparação do esquema, sem levar em conta se é uma migração de uma versão anterior ou se é uma instalação limpa.</span><span class="sxs-lookup"><span data-stu-id="2daac-111">All .ldf files are installed during schema preparation, regardless of whether you are migrating from a previous release or performing a clean installation.</span></span> <span data-ttu-id="2daac-112">Esses arquivos de esquema são instalados na sequência mostrada na lista anterior e estão localizados na \\ pasta de esquema de suporte \\ na mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="2daac-112">These schema files are installed in the sequence shown in the preceding list and are located in the \\Support\\schema folder on the installation media.</span></span>

<span data-ttu-id="2daac-113">As extensões de esquema do Lync Server são replicadas em todos os domínios, o que impacta o tráfego de rede.</span><span class="sxs-lookup"><span data-stu-id="2daac-113">The Lync Server schema extensions are replicated across all domains, which impacts network traffic.</span></span> <span data-ttu-id="2daac-114">Execute a preparação do esquema quando a utilização da rede estiver baixa.</span><span class="sxs-lookup"><span data-stu-id="2daac-114">Run schema preparation at a time when network usage is low.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2daac-115">Se você precisar adicionar suporte para o Microsoft® Office Communicator Mobile 2007 R2 para Java e o Microsoft® Office Communicator Mobile para clientes móveis da Nokia 1,0 à sua implantação do Lync Server 2013, será necessário preparar o esquema do Active Directory para o Microsoft Office Communications Server 2007 R2 durante a instalação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2daac-115">If you need to add support for Microsoft® Office Communicator Mobile 2007 R2 for Java and Microsoft® Office Communicator Mobile for Nokia 1.0 mobile clients to your Lync Server 2013 deployment, you need to prepare the Active Directory schema for Microsoft Office Communications Server 2007 R2 during installation of Lync Server 2013.</span></span> <span data-ttu-id="2daac-116">Para obter o software e a documentação necessários, consulte <A href="https://go.microsoft.com/fwlink/p/?linkid=207172">https://go.microsoft.com/fwlink/p/?linkId=207172</A> .</span><span class="sxs-lookup"><span data-stu-id="2daac-116">For the necessary software and documentation, see <A href="https://go.microsoft.com/fwlink/p/?linkid=207172">https://go.microsoft.com/fwlink/p/?linkId=207172</A>.</span></span>



</div>

<div>

## <a name="adsi-edit"></a><span data-ttu-id="2daac-117">Editor ADSI</span><span class="sxs-lookup"><span data-stu-id="2daac-117">ADSI Edit</span></span>

<span data-ttu-id="2daac-118">Active Directory Service Interfaces Editor (Editor ADSI) é uma ferramenta de administração AD DS que você pode usar para verificar a preparação e a replicação de esquema.</span><span class="sxs-lookup"><span data-stu-id="2daac-118">Active Directory Service Interfaces Editor (ADSI Edit) is an AD DS administration tool that you can use to verify schema preparation and replication.</span></span>

<span data-ttu-id="2daac-119">O Editor ADSI é instalado por padrão quando você instala a função AD DS para transformar um servidor em um controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="2daac-119">ADSI Edit is installed by default when you install the AD DS role to make a server a domain controller.</span></span> <span data-ttu-id="2daac-120">Para o Windows Server 2008 e o Windows Server 2008 R2, o ADSI Edit (Adsiedit. msc) está incluído nas ferramentas de administração de servidor remoto (RSAT).</span><span class="sxs-lookup"><span data-stu-id="2daac-120">For Windows Server 2008 and Windows Server 2008 R2, ADSI Edit (adsiedit.msc) is included with the Remote Server Administration Tools (RSAT).</span></span> <span data-ttu-id="2daac-121">Você também pode instalar o RSAT em servidores de membro de domínio ou servidores autônomos.</span><span class="sxs-lookup"><span data-stu-id="2daac-121">You can also install RSAT on domain member servers or stand-alone servers.</span></span> <span data-ttu-id="2daac-122">O pacote RSAT é copiado a esses servidores por padrão quando o Windows é instalado, mas não é instalado por padrão.</span><span class="sxs-lookup"><span data-stu-id="2daac-122">The RSAT package is copied to these servers by default when you install Windows, but it is not installed by default.</span></span> <span data-ttu-id="2daac-123">Instale as ferramentas individuais usando o Gerenciador de Servidores.</span><span class="sxs-lookup"><span data-stu-id="2daac-123">You install individual tools by using Server Manager.</span></span> <span data-ttu-id="2daac-124">O ADSI Edit está incluído em **Ferramentas de Administração de Funções**, **Ferramentas de Serviços de Domínio Active Directory**, **Ferramentas do Controlador de Domínio do Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="2daac-124">ADSI Edit is included under **Role Administration Tools**, **Active Directory Domain Services Tools**, **Active Directory Domain Controller Tools**.</span></span>

<span data-ttu-id="2daac-125">Para o Windows Server 2003, o ADSI Edit está incluído nas Ferramentas de Suporte.</span><span class="sxs-lookup"><span data-stu-id="2daac-125">For Windows Server 2003, ADSI Edit is included with the Support Tools.</span></span> <span data-ttu-id="2daac-126">As ferramentas de suporte estão disponíveis no CD do Windows Server 2003 na \\ \\ pasta ferramentas de suporte ou você pode baixá-las de "ferramentas de suporte do windows Server 2003 Service Pack 2 32-bit" em [https://go.microsoft.com/fwlink/p/?linkId=125770](https://go.microsoft.com/fwlink/p/?linkid=125770) .</span><span class="sxs-lookup"><span data-stu-id="2daac-126">The Support Tools are available from the Windows Server 2003 CD in the \\SUPPORT\\TOOLS folder, or you can download them from “Windows Server 2003 Service Pack 2 32-bit Support Tools” at [https://go.microsoft.com/fwlink/p/?linkId=125770](https://go.microsoft.com/fwlink/p/?linkid=125770).</span></span> <span data-ttu-id="2daac-127">As instruções para instalar as ferramentas de suporte do CD do produto estão disponíveis em "instalar ferramentas de suporte do Windows" em [https://go.microsoft.com/fwlink/p/?linkId=125771](https://go.microsoft.com/fwlink/p/?linkid=125771) .</span><span class="sxs-lookup"><span data-stu-id="2daac-127">Instructions for installing the Support Tools from the product CD are available from “Install Windows Support Tools” at [https://go.microsoft.com/fwlink/p/?linkId=125771](https://go.microsoft.com/fwlink/p/?linkid=125771).</span></span> <span data-ttu-id="2daac-128">O arquivo Adsiedit.dll é automaticamente registrado quando você instala as ferramentas de suporte.</span><span class="sxs-lookup"><span data-stu-id="2daac-128">Adsiedit.dll is automatically registered when you install the support tools.</span></span> <span data-ttu-id="2daac-129">Se, no entanto, você tiver copiado os arquivos para o computador, deverá executar o comando **regsvr32** para registrar o arquivo adsiedit.dll e executar a ferramenta.</span><span class="sxs-lookup"><span data-stu-id="2daac-129">If, however, you copied the files to your computer, you must run the **regsvr32** command to register the adsiedit.dll file before you can run the tool.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2daac-130">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="2daac-130">In This Section</span></span>

  - [<span data-ttu-id="2daac-131">Executando a preparação do esquema do Active Directory no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2daac-131">Running Active Directory schema preparation in Lync Server 2013</span></span>](lync-server-2013-running-schema-preparation.md)

  - [<span data-ttu-id="2daac-132">Verificando a replicação do esquema do Active Directory no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2daac-132">Verifying Active Directory schema replication in Lync Server 2013</span></span>](lync-server-2013-verifying-schema-replication.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2daac-133">Confira também</span><span class="sxs-lookup"><span data-stu-id="2daac-133">See Also</span></span>


[<span data-ttu-id="2daac-134">Preparando a floresta para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2daac-134">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
[<span data-ttu-id="2daac-135">Preparando domínios para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2daac-135">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

