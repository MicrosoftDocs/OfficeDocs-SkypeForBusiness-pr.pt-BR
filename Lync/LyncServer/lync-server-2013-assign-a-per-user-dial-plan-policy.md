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
ms.openlocfilehash: 9ea17e772bd98501b0d50674a2b82a9abb0e0b38
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043703"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a>Atribuir uma política de plano de discagem por usuário no Lync Server 2013

 


Para concluir a configuração da conta de usuário para usuários do Enterprise Voice ou usuários de conferência discada, o usuário deve receber um plano de discagem. As contas de usuário usarão automaticamente o plano de discagem global ou, se houver um, o plano de discagem no nível do site quando você não atribuir explicitamente um plano de discagem por usuário existente. Se quiser usar o plano de discagem global ou de site para todos os usuários habilitados para o Enterprise Voice, você pode ignorar esta seção.

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a>Para atribuir um plano de discagem usando o painel de controle do Lync Server 2013

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Usuários**.

4.  Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.

5.  Na tabela, clique na conta de usuário para a qual você deseja atribuir um plano de discagem.

6.  No menu **Editar**, clique em **Exibir detalhes**.

7.  Na página **Editar Lync Server**, em **Telefonia**, clique em **Enterprise Voice**.

8.  Clique em **política do plano de discagem**e escolha o plano de discagem desejado.

9.  Clique em **Confirmar**.

Para obter detalhes sobre como configurar planos de discagem, consulte o tópico [Configuring dial Plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) .

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a>Atribuir um plano de discagem por usuário usando cmdlets do Windows PowerShell

Você pode atribuir planos de discagem por usuário com o Windows PowerShell e o cmdlet **Grant-CsdialPlan** . Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>Para atribuir um plano de discagem por usuário a um único usuário

  - O comando a seguir atribui o plano de discagem por usuário RedmondDialPlan ao usuário Ken Myer.
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>Para atribuir um plano de discagem por usuário a vários usuários

  - Este comando atribui o plano de discagem por usuário RedmondDialPlan a todos os usuários que trabalham na cidade de Redmond. Para obter mais informações sobre o parâmetro LdapFilter usado neste comando, consulte a documentação do cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a>Para cancelar a atribuição de um plano de discagem por usuário

  - O comando a seguir retira a atribuição de qualquer plano de discagem por usuário anteriormente atribuído a Ken Myer. Após o plano de discagem por usuário não ser atribuído, Ken Myer será automaticamente gerenciado usando o plano de discagem global, seu plano de discagem de site local (se houver) ou o plano de discagem de escopo de serviço atribuído ao seu registrador ou gateway PSTN. Um plano de discagem de escopo de serviço tem precedência sobre qualquer plano de discagem de site e um plano de discagem de site tem preferência sobre o plano de discagem global.
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\)) .

## <a name="see-also"></a>Confira também


[Configurando planos de discagem no Lync Server 2013](lync-server-2013-configuring-dial-plans.md)  
[Contas de usuário habilitadas para o Lync Server 2013](lync-server-2013-user-accounts-enabled-for-lync-server.md)

