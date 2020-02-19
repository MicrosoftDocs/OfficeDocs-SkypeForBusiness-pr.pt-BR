---
title: 'Lync Server 2013: exibindo informações de política de local'
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
ms.openlocfilehash: f22f5f218f3b9b97b90b26e1f74ec80cd0572e93
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-location-policy-information-in-lync-server-2013"></a>Exibindo informações de política de local no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

No Lync Server 2013, você pode usar a política de local para aplicar configurações relacionadas à funcionalidade avançada 9-1-1 (E9-1-1) e às configurações de local para usuários ou contatos. A política de local determina se o usuário está habilitado para o E9-1-1 e, se estiver, qual vai ser o comportamento de uma chamada de emergência. Por exemplo, é possível usar a política de local para definir o número que constitui uma chamada de emergência (911 nos Estados Unidos), se a segurança da empresa deve ser automaticamente notificada e como a chamada é roteada.

Você pode configurar políticas de local no painel de controle de **rede** do Lync Server 2013. No painel de controle do Lync Server, você pode exibir, criar, modificar ou excluir políticas de local. Use o procedimento a seguir para exibir informações sobre políticas de local. Para obter detalhes sobre como criar ou modificar políticas de local, consulte [criando ou modificando uma política de local no Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).

<div>

## <a name="to-view-information-about-a-location-policy"></a>Para visualizar informações sobre uma política de local

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Configuração de rede** e clique em **Política de local**.

4.  Na página **Política de local**, selecione a política de local que você quer modificar.

5.  No menu **Editar**, clique em **Mostrar detalhes**.
    
    <div>
    

    > [!NOTE]  
    > Você pode visulizar informações apenas de uma política de local por vez.

    
    </div>

Uma política única, chamada de Global, existe por padrão e não pode ser excluída ou renomeada. Porém, você pode modificar a política Global. Essa política será aplicada a todos os usuários e contatos, a não ser que você crie políticas de sites ou políticas por usuário. As políticas por usuário devem ser aplicadas a usuários específicos.

</div>

<div>

## <a name="see-also"></a>Confira também


[Criando ou modificando uma política de local no Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[Criar políticas de local no Lync Server 2013](lync-server-2013-create-location-policies.md)  
[Criar ou modificar um site de rede no Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)  


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

