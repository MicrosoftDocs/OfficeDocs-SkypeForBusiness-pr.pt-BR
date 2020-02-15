---
title: 'Lync Server 2013: usuários domésticos em um servidor ou aparelho de filial persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Home users on a Survivable Branch Appliance or Server
ms:assetid: faf1ebb9-6d7d-4a58-8ff7-801b7b31d3ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413066(v=OCS.15)
ms:contentKeyID: 48185926
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6efd5991260ffeec3c6279857625eadfe34eca4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047449"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>Usuários domésticos em um aparelho de filial persistente ou servidor no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-12-10_

O processo de Hospedagem de usuários em um aparelho de filial persistente ou servidor de filial persistente é semelhante ao processo de Hospedagem de usuários em um pool de front-ends. Execute o processo de aparelho de filial persistente ou servidor de filial persistente no site central.

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a>Para usuários domésticos no Servidor ou Aplicativo de Filial Persistente ou Servidor de Filial Persistente

1.  Antes de mover os usuários para o servidor de filial persistente ou servidor de filial persistente, abra o Shell de gerenciamento do Lync Server e faça o seguinte:
    
      - Execute o cmdlet **Test-CsPstnOutboundCall** para verificar se o servidor de filial persistente está em execução e se a conectividade PSTN (rede telefônica pública comutada) está configurada. Se você precisar modificar as propriedades do gateway PSTN, use o cmdlet **Set-CsPstnGateway**.
    
      - Execute o cmdlet **Get-CsVoicePolicy** para verificar se os usuários que serão hospedados no servidor de filial persistente têm a política de roteamento VoIP apropriada. Se você precisar modificar a política VoIP, use o cmdlet **Set-CsVoicePolicy**.
    
      - Execute o cmdlet **Get-CsVoicemailReroutingConfiguration** para verificar se as configurações de redirecionamento de caixa postal estão configuradas. Se você precisar modificar o configurações de redirecionamento de caixa postal, use o cmdlet **Set-CsVoicemailReroutingConfiguration**.

2.  No Shell de gerenciamento do Lync Server, execute o cmdlet **move-CsUser** para mover usuários domésticos.

<div>


> [!NOTE]  
> Você também pode usar o painel de controle do Lync Server para verificar os pré-requisitos e usuários domésticos.



</div>

<div>


> [!NOTE]  
> Os usuários hospedados em um aparelho de filial persistente do Lync Server não podem criar novas salas de chat ou exibir o cartão de sala para salas existentes.



</div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[Get-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[Get-CsVoicemailReroutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

