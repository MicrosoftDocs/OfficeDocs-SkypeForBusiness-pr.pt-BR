---
title: 'Lync Server 2013: Personalizando a instalação do cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Customizing client installation
ms:assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204934(v=OCS.15)
ms:contentKeyID: 48184254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd099f5d57174eb02733abd70bb99a91679a1328
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829748"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="customizing-client-installation-in-lync-server-2013"></a><span data-ttu-id="154ce-102">Personalizando a instalação do cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="154ce-102">Customizing client installation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="154ce-103">_**Tópico da última modificação:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="154ce-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="154ce-104">Os administradores empresariais podem personalizar a instalação do Office 2013 baseada no Windows Installer (. msi) usando os métodos discutidos nesta seção.</span><span class="sxs-lookup"><span data-stu-id="154ce-104">Enterprise administrators can customize the Office 2013 Windows Installer-based (.msi) installation by using the methods discussed in this section.</span></span> <span data-ttu-id="154ce-105">Como nenhuma ferramenta tem todas as opções de personalização, você provavelmente usará uma combinação desses métodos em sua implantação do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="154ce-105">Because no single tool provides all customization options, you’ll likely use a combination of these methods in your Lync 2013 deployment.</span></span> <span data-ttu-id="154ce-106">No mínimo, você pode usar as ferramentas descritas nas seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="154ce-106">At a minimum, you might use the tools described in the following sections:</span></span>

  - <span data-ttu-id="154ce-107">[Usar a ferramenta de personalização do Office (OCT) no Lync Server 2013](lync-server-2013-using-the-office-customization-tool-oct.md) para personalizar opções e recursos de configuração do Lync e outros programas do Office.</span><span class="sxs-lookup"><span data-stu-id="154ce-107">[Using the Office Customization Tool (OCT) in Lync Server 2013](lync-server-2013-using-the-office-customization-tool-oct.md) to customize setup options and features for Lync and other Office programs.</span></span>

  - <span data-ttu-id="154ce-108">[Usando config. xml para executar tarefas de instalação no Lync Server 2013](lync-server-2013-using-config-xml-to-perform-installation-tasks.md) para especificar o caminho do ponto de instalação da rede e executar a instalação silenciosa.</span><span class="sxs-lookup"><span data-stu-id="154ce-108">[Using Config.xml to perform installation tasks in Lync Server 2013](lync-server-2013-using-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>

  - <span data-ttu-id="154ce-109">[Usando as opções de linha de comando de configuração no Lync Server 2013](lync-server-2013-using-setup-command-line-options.md) para especificar o arquivo config. XML a ser usado durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="154ce-109">[Using Setup command-line options in Lync Server 2013](lync-server-2013-using-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>

  - <span data-ttu-id="154ce-110">[Configurando as políticas de inicialização do cliente no Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) usando o snap-in do MMC do editor de objeto de política de grupo.</span><span class="sxs-lookup"><span data-stu-id="154ce-110">[Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>

<span data-ttu-id="154ce-111">Provavelmente, haverá outras opções que você desejará configurar ao implantar o pacote de produtos do Office.</span><span class="sxs-lookup"><span data-stu-id="154ce-111">There will probably be other options you’ll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="154ce-112">Os tópicos desta seção fornecem uma visão geral dessas ferramentas de personalização e discutem considerações específicas do Lync.</span><span class="sxs-lookup"><span data-stu-id="154ce-112">The topics in this section give an overview of these customization tools and discuss Lync-specific considerations.</span></span> <span data-ttu-id="154ce-113">Estão inclusos links para a ajuda detalhada do Office referente a cada ferramenta.</span><span class="sxs-lookup"><span data-stu-id="154ce-113">Included are links to detailed Office help for each tool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

