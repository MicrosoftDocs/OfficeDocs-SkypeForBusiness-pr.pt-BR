---
title: 'Lync Server 2013: Personalizando a instalação do cliente'
description: 'Lync Server 2013: Personalizando a instalação do cliente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Customizing client installation
ms:assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204934(v=OCS.15)
ms:contentKeyID: 48184254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8dd1942c298ccbc8b6a2950baf4f24cc2f797a92
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561137"
---
# <a name="customizing-client-installation-in-lync-server-2013"></a><span data-ttu-id="90587-103">Personalizando a instalação do cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90587-103">Customizing client installation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90587-104">_**Última modificação do tópico:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="90587-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="90587-105">Os administradores corporativos podem personalizar a instalação do Office 2013 com base no Windows Installer (. msi) usando os métodos discutidos nesta seção.</span><span class="sxs-lookup"><span data-stu-id="90587-105">Enterprise administrators can customize the Office 2013 Windows Installer-based (.msi) installation by using the methods discussed in this section.</span></span> <span data-ttu-id="90587-106">Como nenhuma ferramenta única fornece todas as opções de personalização, você provavelmente usará uma combinação desses métodos em sua implantação do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="90587-106">Because no single tool provides all customization options, you’ll likely use a combination of these methods in your Lync 2013 deployment.</span></span> <span data-ttu-id="90587-107">Você poderá usar pelo menos as ferramentas descritas nas seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="90587-107">At a minimum, you might use the tools described in the following sections:</span></span>

  - <span data-ttu-id="90587-108">[Usando a ferramenta de personalização do Office (OCT) no Lync Server 2013](lync-server-2013-using-the-office-customization-tool-oct.md) para personalizar opções e recursos de instalação para o Lync e outros programas do Office.</span><span class="sxs-lookup"><span data-stu-id="90587-108">[Using the Office Customization Tool (OCT) in Lync Server 2013](lync-server-2013-using-the-office-customization-tool-oct.md) to customize setup options and features for Lync and other Office programs.</span></span>

  - <span data-ttu-id="90587-109">[Usando o Config.xml para realizar tarefas de instalação no Lync Server 2013](lync-server-2013-using-config-xml-to-perform-installation-tasks.md) para especificar o caminho do ponto de instalação de rede e executar a instalação silenciosa.</span><span class="sxs-lookup"><span data-stu-id="90587-109">[Using Config.xml to perform installation tasks in Lync Server 2013](lync-server-2013-using-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>

  - <span data-ttu-id="90587-110">[Usando opções de linha de comando da instalação no Lync Server 2013](lync-server-2013-using-setup-command-line-options.md) para especificar o arquivo de Config.xml a ser usado durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="90587-110">[Using Setup command-line options in Lync Server 2013](lync-server-2013-using-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>

  - <span data-ttu-id="90587-111">[Configuração de políticas de inicialização do cliente no Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) usando o snap-in do MMC do editor de objeto de diretiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="90587-111">[Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>

<span data-ttu-id="90587-p102">Provavelmente, haverá outras opções que você desejará configurar ao implantar o pacote de produtos do Office. Os tópicos desta seção oferecem uma visão geral dessas ferramentas de personalização e abordam considerações específicas do Lync. Estão inclusos links para a ajuda detalhada do Office referente a cada ferramenta.</span><span class="sxs-lookup"><span data-stu-id="90587-p102">There will probably be other options you’ll want to configure as you deploy the Office suite of products. The topics in this section give an overview of these customization tools and discuss Lync-specific considerations. Included are links to detailed Office help for each tool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

