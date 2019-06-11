---
title: 'Lync Server 2013: Usuários domésticos em um Home users on a Aparelho de Filial Persistente ou Servidor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Home users on a Survivable Branch Appliance or Server
ms:assetid: faf1ebb9-6d7d-4a58-8ff7-801b7b31d3ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413066(v=OCS.15)
ms:contentKeyID: 48185926
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceabf8fe7d8f9068e60bbc20406d2496f815b04b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>Usuários domésticos em um Home users on a Aparelho de Filial Persistente ou Servidor no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-12-10_

O processo de Hospedagem de usuários em um aparelho de ramificação sobreviventes ou um servidor de ramificação sobreviventes é semelhante ao processo de Hospedagem de usuários em um pool de front-ends. Realize o aplicativo de ramificação sobreviventes ou o procedimento do servidor de ramificação sobreviventes no site central.

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a>Para usuários domésticos em um aparelho de ramificação sobreviventes ou em um servidor de ramificação sobreviventes

1.  Antes de mover os usuários para o servidor de ramificação sobreviventes ou o servidor de ramificação sobreviventes, abra o Shell de gerenciamento do Lync Server e, em seguida, faça o seguinte:
    
      - Execute o cmdlet **Test-CsPstnOutboundCall** para verificar se o servidor de ramificação sobreviventes está em execução e se a conectividade PSTN (rede telefônica pública comutada) está configurada. Se você precisar modificar as propriedades do gateway PSTN, use o cmdlet **set-CsPstnGateway**.
    
      - Execute o cmdlet **Get-CsVoicePolicy** para verificar se os usuários que serão hospedados no servidor de ramificação sobreviventes têm a política de roteamento de VoIP apropriada. Se você precisar modificar a política de VoIP, use o cmdlet **set-CsVoicePolicy**.
    
      - Execute o cmdlet **Get-CsVoicemailReroutingConfiguration** para verificar se as configurações de redirecionamento da caixa postal estão definidas. Se precisar modificar as configurações de redirecionamento da caixa postal, use o cmdlet **set-CsVoicemailReroutingConfiguration**.

2.  No Shell de gerenciamento do Lync Server, execute o cmdlet **move-CsUser** para mover os usuários domésticos.

<div>


> [!NOTE]  
> Você também pode usar o painel de controle do Lync Server para verificar pré-requisitos e usuários domésticos.



</div>

<div>


> [!NOTE]  
> Os usuários que estiverem hospedados em um aparelho de ramificação de Lync do Lync Server não poderão criar novas salas de chat ou exibir o cartão de sala para salas existentes.



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

