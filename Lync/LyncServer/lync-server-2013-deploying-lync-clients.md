---
title: 'Lync Server 2013: Implantando clientes do Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync clients
ms:assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204827(v=OCS.15)
ms:contentKeyID: 48183925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d7f4497fb6842befba3f5facf5de023b94b4a76
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-clients-in-lync-server-2013"></a>Implantando clientes do Lync no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-03_

O Lync 2013 introduz uma abordagem diferente para a implantação do cliente. Em uma partida de versões anteriores, o Lync 2013 não tem mais seu próprio instalador. Em vez disso, o Lync está incluído no programa de instalação do Office 2013. Para implantar o Lync 2013 em seus usuários, você pode usar os métodos de instalação e ferramentas de personalização do Office 2013.

  - **Office 2013 o Windows Installer** é um pacote de instalação baseado no Windows Installer que consiste em vários arquivos MSI. Um pacote de núcleo MSI de linguagem neutra é combinado com um ou mais pacotes de linguagem específica para fazer um produto completo. A instalação reúne os pacotes individuais e efetua a personalização e tarefas de manutenção durante e após a instalação do Office nos computadores dos usuários. Os tópicos desta seção descrevem como usar e personalizar o instalador do Windows do Office 2013 para implantar o Lync 2013.

  - O **Office 2013 clique para executar** é um programa de instalação que transmite os arquivos de instalação do Office para o usuário a partir do portal do Microsoft Office 365. Os administradores podem personalizar a instalação utilizando a Ferramenta de Implantação do Office para Clique para Executar. Como o Office 2013 com Clique para executar é usado principalmente no ambiente do Microsoft Office 365, esse método de instalação não está descrito em detalhes nesta seção. Informações detalhadas sobre como usar e personalizar a instalação do clique para executar estão disponíveis na documentação do Office 2013 Resource Kit. Os administradores também podem baixar os arquivos de código-fonte do Office 2013 e os arquivos de idioma do Office para um local local, o que é útil quando você deseja minimizar a demanda na rede ou impedir que os usuários instalem o software da Internet por causa de requisitos de segurança corporativa.

Os tópicos desta seção se concentram em como implantar clientes usando o instalador baseado em MSI do Office 2013. Sua referência principal deve ser a documentação do Office 2013 Resource Kit, que descreve em detalhes como preparar sua infraestrutura, personalizar a instalação e implantar o Office 2013. No entanto, você deve usar a documentação do Office em conjunto com os tópicos desta seção, que apontam as considerações de implantação específicas do Lync 2013.

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>O suplemento de reunião online do Lync 2013, que dá suporte ao gerenciamento de reuniões dentro do cliente de mensagens e colaboração do Outlook, é instalado automaticamente com o Lync 2013.</P>
> <LI>
> <P>O programa de instalação do Office 2013 não desinstala versões anteriores do Lync ou do Office Communicator. O cliente do Lync 2013 é instalado lado a lado com outros clientes do Lync ou do Office Communicator</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Personalizando a instalação do cliente no Lync Server 2013](lync-server-2013-customizing-client-installation.md)

  - [Personalizando o comportamento do Lync e a interface do usuário no Lync Server 2013](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [Personalizando o suplemento de reunião online no Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [Configurando a página de ingresso na reunião no Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md)

  - [Configurando as versões de cliente com suporte no Lync Server 2013](lync-server-2013-configuring-supported-client-versions.md)

  - [Configurando o modo de privacidade de presença avançada no Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

