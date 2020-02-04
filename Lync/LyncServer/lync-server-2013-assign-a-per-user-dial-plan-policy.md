---
title: 'Lync Server 2013: atribuir uma política de plano de discagem por usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user dial plan policy
ms:assetid: 9fea861f-7770-4cae-9b1f-2a960595bfc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688156(v=OCS.15)
ms:contentKeyID: 49733760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2bc62981a69b1260ba5f2fbaeabc112553b85f5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722961"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a>Atribuir uma política de plano de discagem por usuário no Lync Server 2013

 


Para concluir a configuração da conta de usuário para usuários do Enterprise Voice ou usuários de conferências discadas, o usuário deve receber um plano de discagem. As contas de usuário usarão automaticamente o plano de discagem global ou, se houver, o plano de discagem em nível de site quando você não atribui explicitamente um plano de discagem por usuário existente. Se quiser usar o plano global ou de discagem de site para todos os usuários habilitados para o Enterprise Voice, você pode ignorar esta seção.

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a>Para atribuir um plano de discagem usando o painel de controle do Lync Server 2013

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Usuários**.

4.  Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.

5.  Na tabela, clique na conta de usuário para a qual você deseja atribuir um plano de discagem.

6.  No menu **Editar**, clique em **Exibir detalhes**.

7.  Na página **Editar usuário do Lync Server** , em **telefonia**, clique em **Enterprise Voice**.

8.  Clique em **política de plano de discagem**e escolha o plano de discagem desejado.

9.  Clique em **Confirmar**.

Para obter detalhes sobre como configurar planos de discagem, consulte o tópico [Configurando planos de discagem no Lync Server 2013](lync-server-2013-configuring-dial-plans.md) .

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a>Atribuir um plano de discagem por usuário usando cmdlets do Windows PowerShell

Você pode atribuir planos de discagem por usuário com o Windows PowerShell e o cmdlet **Grant-CsdialPlan** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>Atribuir um plano de discagem por usuário a um único usuário

  - O comando a seguir atribui o plano de discagem por usuário RedmondDialPlan ao usuário Ken Myer.
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>Atribuir um plano de discagem por usuário a vários usuários

  - Esse comando atribui o plano de discagem por usuário RedmondDialPlan a todos os usuários que trabalham na cidade de Redmond. Para obter mais informações sobre o parâmetro LdapFilter usado neste comando, consulte a documentação do cmdlet [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a>Retirar a atribuição de uma plano de discagem por usuário

  - O comando a seguir cancelará a atribuição de um plano de discagem por usuário anteriormente atribuído a Ken Myer. Após a atribuição do plano de discagem por usuário, Ken Myer será automaticamente gerenciado usando o plano de discagem global, seu plano de discagem de site local (se houver) ou o plano de discagem de escopo de serviço atribuído ao registrador ou ao gateway PSTN. Um plano de discagem de escopo de serviço tem precedência sobre qualquer plano de discagem de site e um plano de discagem de site tem prioridade sobre o plano de discagem global.
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\)) .

## <a name="see-also"></a>Confira também


[Configurando planos de discagem no Lync Server 2013](lync-server-2013-configuring-dial-plans.md)  
[Contas de usuário habilitadas para o Lync Server 2013](lync-server-2013-user-accounts-enabled-for-lync-server.md)

