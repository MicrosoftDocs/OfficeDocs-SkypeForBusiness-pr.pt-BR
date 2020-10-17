---
title: 'Lync Server 2013: Implantando clientes Lync'
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
ms.openlocfilehash: 3d79eb803b7dd05a7bb03b1189f3a6a4294ec104
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525258"
---
# <a name="deploying-lync-clients-in-lync-server-2013"></a>Implantando clientes Lync no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-03_

O Lync 2013 introduz uma abordagem diferente para a implantação do cliente. Em uma partida de versões anteriores, o Lync 2013 não tem mais seu próprio instalador. Em vez disso, o Lync está incluído no programa de instalação do Office 2013. Para implantar o Lync 2013 em seus usuários, você pode usar os métodos de instalação e as ferramentas de personalização do Office 2013.

  - O **Office 2013 Windows Installer** é um pacote de instalação baseado no Windows Installer que consiste em vários arquivos MSI. Um pacote de núcleo MSI de linguagem neutra é combinado com um ou mais pacotes de linguagem específica para fazer um produto completo. A instalação reúne os pacotes individuais e efetua a personalização e tarefas de manutenção durante e após a instalação do Office nos computadores dos usuários. Os tópicos desta seção descrevem como usar e personalizar o Office 2013 Windows Installer para implantar o Lync 2013.

  - O **Office 2013 clique para executar** é um programa de instalação que transmite arquivos de instalação do Office para o usuário a partir do centro de administração do Microsoft 365. Os administradores podem personalizar a instalação utilizando a Ferramenta de Implantação do Office para Clique para Executar. Como o Office 2013 clique para executar é usado principalmente no ambiente do Microsoft 365, este método de instalação não é descrito em detalhes nesta seção. Informações detalhadas sobre como usar e personalizar a instalação clique para executar estão disponíveis na documentação do kit de recursos do Office 2013. Os administradores também podem baixar os arquivos de programa e de origem do Office 2013 clique para executar em um local local, o que é útil quando você deseja minimizar a demanda na rede ou impedir que os usuários instalem software da Internet por causa dos requisitos de segurança corporativos.

Os tópicos desta seção concentram-se em como implantar clientes usando o instalador baseado em MSI do Office 2013. Sua referência principal deve ser a documentação do kit de recursos do Office 2013, que descreve detalhadamente como preparar sua infraestrutura, personalizar a instalação e implantar o Office 2013. No entanto, você deve usar a documentação do Office em conjunto com os tópicos nesta seção, que apontam as considerações de implantação específicas para o Lync 2013.

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>O suplemento de reunião online do Lync 2013, que oferece suporte ao gerenciamento de reuniões a partir do cliente de mensagens e colaboração do Outlook, é instalado automaticamente com o Lync 2013.</P>
> <LI>
> <P>O programa de instalação do Office 2013 não desinstala versões anteriores do Lync ou Office Communicator. O cliente do Lync 2013 é instalado lado a lado com outros clientes do Lync ou do Office Communicator</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Personalizando a instalação do cliente no Lync Server 2013](lync-server-2013-customizing-client-installation.md)

  - [Personalizando o comportamento do Lync e a interface do usuário no Lync Server 2013](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [Personalizando o suplemento reunião online no Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [Configurando a página de ingresso na reunião no Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md)

  - [Configurando as versões de cliente suportadas no Lync Server 2013](lync-server-2013-configuring-supported-client-versions.md)

  - [Configurando o modo de privacidade de presença avançada no Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

