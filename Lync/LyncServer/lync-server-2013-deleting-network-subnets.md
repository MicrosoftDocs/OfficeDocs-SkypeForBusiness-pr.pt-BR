---
title: 'Lync Server 2013: excluindo sub-redes de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network subnets
ms:assetid: c1850f38-40a3-48c9-b6f1-f181c5e63b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721873(v=OCS.15)
ms:contentKeyID: 49733806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c87ca1cfd91344d8f8cbb0b320c70def47bf5ac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740961"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-subnets-in-lync-server-2013"></a>Excluindo sub-redes de rede no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

Você pode usar o procedimento a seguir para excluir uma sub-rede. No painel de controle do Lync Server, você pode criar, modificar ou excluir uma sub-rede de rede. Para obter detalhes sobre como criar ou modificar sub-redes de rede, consulte [criar ou modificar sub-redes de rede no Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).

Na maioria das implantações do Microsoft Lync Server 2013 em que o controle de admissão de chamadas (CAC) é implementado, normalmente há um grande número de sub-redes. Por isso, geralmente é melhor configurar sub-redes a partir do Shell de gerenciamento do Lync Server. Em seguida, você pode chamar **New-CsNetworkSubnet** em conjunto com o cmdlet **Import-CSV**do Windows PowerShell. Ao usar esses cmdlets juntos, você pode ler as configurações de sub-rede a partir de um arquivo de valores separados por vírgulas (. csv) e criar várias sub-redes ao mesmo tempo. Para obter exemplos de como criar sub-redes a partir de um arquivo. csv, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).

<div>

## <a name="to-delete-a-network-subnet"></a>Para excluir uma sub-rede de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, clique em **sub-rede**.

4.  Na página **sub-rede** , clique na sub-rede que você deseja excluir.
    
    <div>
    

    > [!NOTE]  
    > Você pode excluir mais de uma sub-rede de cada vez. Para fazer isso, pressione CTRL e selecione várias sub-redes enquanto mantém a tecla CTRL pressionada. Ou, para selecionar todas as sub-redes, clique em <STRONG>selecionar tudo</STRONG> no menu <STRONG>Editar</STRONG> .

    
    </div>

5.  No menu **Editar** , clique em **excluir**.

6.  Clique em **OK**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Criar ou modificar sub-redes de rede no Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

