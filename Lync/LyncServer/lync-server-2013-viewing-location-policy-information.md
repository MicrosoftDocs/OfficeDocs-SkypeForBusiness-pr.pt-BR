---
title: 'Lync Server 2013: exibindo informações de política de localização'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing location policy information
ms:assetid: 14e41bcb-ea0a-49c2-99b3-1f61fc34416d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520954(v=OCS.15)
ms:contentKeyID: 48183489
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f68ad38ffbc8bb1b4abdfbf8119add7d9f965e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-location-policy-information-in-lync-server-2013"></a>Exibindo informações de política de localização no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

No Lync Server 2013, você pode usar a política de localização para aplicar configurações relacionadas à funcionalidade Enhanced 9-1-1 (E9-1-1) e às configurações de localização para usuários ou contatos. A política de localização determina se um usuário está habilitado para E9-1-1 e, em caso afirmativo, qual é o comportamento de uma chamada de emergência. Por exemplo, você pode usar a política de localização para definir qual número constitui uma chamada de emergência (por exemplo, 911 nos Estados Unidos), se a segurança corporativa deve ser notificada automaticamente e como a chamada deve ser roteada.

Você pode configurar as políticas de localização do grupo de **configuração de rede** no painel de controle do Lync Server 2013. No painel de controle do Lync Server, você pode exibir, criar, modificar ou excluir políticas de localização. Use o procedimento a seguir para exibir informações sobre as políticas de localização. Para obter detalhes sobre como criar ou modificar as políticas de localização, consulte [criando ou modificando uma política de localização no Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).

<div>

## <a name="to-view-information-about-a-location-policy"></a>Para exibir informações sobre uma política de localização

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, clique em **política de localização**.

4.  Na página **política de localização** , selecione a política de localização que você deseja modificar.

5.  No menu **Editar**, clique em **Exibir detalhes**.
    
    <div>
    

    > [!NOTE]  
    > Você só pode exibir informações sobre uma política de localização de cada vez.

    
    </div>

Uma única política, chamada global, existe por padrão e não pode ser excluída ou renomeada. No entanto, você pode modificar a política global. Esta política será aplicada a todos os usuários e contatos, a menos que você crie políticas de site ou políticas por usuário. Políticas por usuário devem ser aplicadas a usuários específicos.

</div>

<div>

## <a name="see-also"></a>Confira também


[Criando ou modificando uma política de localização no Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[Criar políticas de localização no Lync Server 2013](lync-server-2013-create-location-policies.md)  
[Criar ou modificar um site da rede no Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)  


[New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  
[Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy)  
[Remove-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  
[Get-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

