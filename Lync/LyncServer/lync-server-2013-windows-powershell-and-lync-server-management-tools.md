---
title: 'Lync Server 2013: ferramentas de gerenciamento do Windows PowerShell e do Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell and Lync Server 2013 management tools
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59893869
ms.date: 07/20/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1acd743d3737232c6e6681b84e524549258d5ffe
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535338"
---
# <a name="windows-powershell-and-lync-server-2013-management-tools"></a>Ferramentas de gerenciamento do Windows PowerShell e do Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2016-07-20_

No Microsoft Lync Server 2013, as ferramentas de gerenciamento são implementadas usando o Windows PowerShell. O Windows PowerShell inclui um ambiente de linha de comando, comandos específicos ao produto e uma linguagem de script completa. As ferramentas do Lync Server 2013 que são implementadas usando o Windows PowerShell incluem o seguinte:

  - **Construtor de topologias**. Você usa o construtor de topologias para criar, ajustar e publicar sua topologia planejada e valida sua topologia antes de iniciar instalações de servidor. Quando você instala o Lync Server 2013 em servidores individuais, os servidores lêem a topologia publicada como parte do processo de instalação e o programa de instalação implanta o servidor conforme indicado na topologia. Após a configuração, as informações de configuração são automaticamente replicadas para todos os servidores. Os componentes podem ser adicionados à sua implantação apenas usando o construtor de topologias.

  - **Shell de gerenciamento do Lync Server**. Você pode usar o Shell de gerenciamento do Lync Server para o gerenciamento completo de linha de comando de sua implantação.

  - **Painel de controle do Lync Server**. Você pode usar a interface do usuário do painel de controle do Microsoft Lync Server 2013 para gerenciar as tarefas mais comuns em sua implantação.

Essas ferramentas usam os cmdlets do Windows PowerShell para gerenciamento de sua implantação, incluindo aproximadamente 550 cmdlets específicos ao produto. Os cmdlets de segurança incluídos no Lync Server 2013 são usados principalmente para gerenciar a autenticação e os direitos e permissões do usuário. Uma ampla variedade de cmdlets está disponível para o gerenciamento da autenticação, incluindo cmdlets para autenticação de certificado e de PIN (número de identificação pessoal). Além disso, vários cmdlets permitem que você use o novo recurso de controle de acesso de Role-Based (RBAC) para delegar o controle administrativo do Lync Server 2013. Para obter detalhes sobre os cmdlets do Lync Server, consulte [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).

Os recursos de segurança de script para Windows PowerShell são projetados especificamente para ajudar a impedir alguns dos problemas de segurança relacionados a script de tecnologias mais antigas, incluindo o Microsoft Visual Basic Scripting Edition (VBScript). Os recursos de segurança do Windows PowerShell têm como objetivo a criação de um ambiente no qual os usuários não podem executar facilmente ou sem intenção. Por padrão, os recursos de segurança do Windows PowerShell estão habilitados. É possível modificar o estado desses recursos a fim de acomodar suas necessidades de script e diversas metas de segurança. Isso sem mencionar que o shell impossibilita a execução de scripts pelos usuários. Em vez disso, o dificulta—por padrão—a execução sem intenção de scripts pelos usuários. Para obter detalhes, consulte segurança de scripts do Windows PowerShell em [https://go.microsoft.com/fwlink/p/?LinkId=213145](https://go.microsoft.com/fwlink/p/?linkid=213145) .

</div>

<span> </span>

</div>

</div>

</div>

