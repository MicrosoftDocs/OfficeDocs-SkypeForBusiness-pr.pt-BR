---
title: 'Lync Server 2013: Ferramentas de gerenciamento do Windows PowerShell e do Lync Server'
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
ms.openlocfilehash: dbfd15ff3c1047f04a6878b65a3d16e63bac490b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-and-lync-server-2013-management-tools"></a>Ferramentas de gerenciamento do Windows PowerShell e do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2016-07-20_

No Microsoft Lync Server 2013, as ferramentas de gerenciamento são implementadas usando o Windows PowerShell. O Windows PowerShell inclui um ambiente de linha de comando, comandos específicos do produto e uma linguagem de script completa. As ferramentas do Lync Server 2013 implementadas usando o Windows PowerShell incluem o seguinte:

  - **Construtor de topologias**. Você usa o construtor de topologias para criar, ajustar e publicar sua topologia planejada e valida sua topologia antes de iniciar instalações de servidor. Quando você instala o Lync Server 2013 em servidores individuais, os servidores lêem a topologia publicada como parte do processo de instalação, e o programa de instalação implanta o servidor conforme direcionado na topologia. After setup, configuration information is automatically replicated to all servers. Components can be added to your deployment only by using Topology Builder.

  - **Shell de gerenciamento do Lync Server**. Você pode usar o Shell de gerenciamento do Lync Server para o gerenciamento de linha de comando completo da sua implantação.

  - **Painel de controle do Lync Server**. Você pode usar a interface do usuário do painel de controle do Microsoft Lync Server 2013 para gerenciar as tarefas mais comuns na sua implantação.

Essas ferramentas usam cmdlets do Windows PowerShell para o gerenciamento da sua implantação, incluindo cmdlets próximos a 550 cmdlets específicos do produto. Os cmdlets de segurança incluídos no Lync Server 2013 são usados principalmente para gerenciar autenticação e direitos e permissões de usuário. Uma ampla variedade de cmdlets está disponível para o gerenciamento da autenticação, incluindo cmdlets para autenticação de certificado e de PIN (número de identificação pessoal). Além disso, vários cmdlets permitem que você use o novo recurso de controle de acesso baseado em função (RBAC) para delegar o controle administrativo do Lync Server 2013. Para obter detalhes sobre os cmdlets do Lync Server, consulte [Shell de gerenciamento do Lync server 2013](lync-server-2013-lync-server-management-shell.md).

Os recursos de segurança de script para Windows PowerShell foram projetados especificamente para ajudar a prevenir alguns problemas de segurança relacionados a scripts de tecnologias mais antigas, incluindo o Microsoft Visual Basic Scripting Edition (VBScript). Os recursos de segurança do Windows PowerShell destinam-se a criar um ambiente no qual os usuários não podem executar scripts de forma fácil ou desconhecida. Por padrão, os recursos de segurança do Windows PowerShell estão habilitados. Você pode modificar o estado desses recursos para atender às suas necessidades de script e cumprir vários objetivos de segurança. Isso não quer dizer que o shell impossibilite os usuários de executar scripts. Em vez disso, o shell dificulta, por padrão, que os usuários executem scripts sem perceber. Para obter detalhes, consulte segurança de script do [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145)Windows PowerShell em.

</div>

<span> </span>

</div>

</div>

</div>

