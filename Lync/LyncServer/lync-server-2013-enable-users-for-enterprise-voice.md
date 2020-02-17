---
title: 'Lync Server 2013: habilitar usuários para o Enterprise Voice'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for Enterprise Voice
ms:assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413011(v=OCS.15)
ms:contentKeyID: 48185800
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c48f701f9396c43337e2723f0dc83a8eda8d96ee
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046684"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-enterprise-voice-in-lync-server-2013"></a>Habilitar usuários para o Enterprise Voice no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Após instalar arquivos para um ou mais servidores de mediação, configurar roteamento de chamadas de saída e opcionalmente implantar um ou mais recursos avançados do Enterprise Voice, você pode usar os seguintes procedimentos para permitir que um usuário faça chamadas usando o Enterprise Voice:

<div>


> [!NOTE]  
> Dos procedimentos a seguir, somente o primeiro pode ser executado usando o painel de controle do Lync Server. Para obter os procedimentos restantes, você pode usar somente o Shell de gerenciamento do Lync Server.



</div>

  - Habilitar a conta de usuário para o Enterprise Voice.

  - (Opcional) Atribuir a conta de usuário com uma política de voz específica do usuário.

  - (Opcional) Atribuir a conta do usuário com um plano de discagem específico do usuário.

<div>

## <a name="to-enable-a-user-account-for-enterprise-voice"></a>Para habilitar uma conta de usuário para o Enterprise Voice

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Usuários**.

4.  Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.

5.  Na tabela, clique na conta de usuário que você deseja habilitar para o Enterprise Voice.

6.  No menu **Editar**, clique em **Exibir detalhes**.

7.  Na página **Editar Lync Server**, em **Telefonia**, clique em **Enterprise Voice**.

8.  Clique em **URI de linha** e digite um número de telefone único e normalizado (por exemplo, tel:+14255550200).

9.  Clique em **Confirmar**.

Para concluir a habilitação de um usuário para o Enterprise Voice, certifique-se de que o usuário é atribuído a uma política de voz e um plano de discagem, seja global (atribuído por padrão) ou específico do usuário.

Por padrão, todos os usuários são atribuídos com uma política de voz global e plano de discagem. Se uma política de voz ou plano de discagem existe no nível do site para o site na qual a conta do usuário está hospedada, estas políticas de site serão aplicadas automaticamente ao usuário. Para aplicar uma política de voz por usuário ou plano de discagem para um usuário, você deve executar os cmdlets **Grant-CsVoicePolicy** e **Grant-CsDialPlan**. Para obter detalhes, consulte a documentação do [Shell de gerenciamento do Lync Server 2013](lync-server-2013-lync-server-management-shell.md) .

</div>

<div>

## <a name="voice-policy-assignment"></a>Atribuição da política de voz

As políticas de voz globais e no nível do site são atribuídas automaticamente a todas as contas de usuário habilitadas para o Enterprise Voice. Também é possível criar políticas de voz que são aplicadas a usuários ou grupos específicos. Estas políticas por usuário devem ser atribuídas explicitamente aos usuários ou grupos. Se você deseja usar a política de voz global ou de site para todos os usuários que estão habilitados para o Enterprise Voice, você pode ignorar esta seção e continuar a discar a atribuição do plano de discagem mais adiante neste tópico.

<div>

## <a name="to-assign-a-user-specific-voice-policy"></a>Para atribuir uma política de voz específica do usuário

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Para atribuir uma política de voz do usuário existente para um usuário, execute o seguinte no prompt de comando:
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    Por exemplo:
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    Neste exemplo, o usuário com o nome de exibição Bob Kelly recebe a política de voz com o nome **chamada voicepolicyjapan**.

Para obter detalhes sobre como atribuir uma política de voz específica do usuário ou sobre a execução do cmdlet **Grant-CsVoicePolicy** , consulte a documentação do [Shell de gerenciamento do Lync Server 2013](lync-server-2013-lync-server-management-shell.md) .

</div>

</div>

<span id="BKMK_DialPlanAssignment"></span>

<div>

## <a name="dial-plan-assignment"></a>Atribuição do plano de discagem

Para concluir a configuração da conta de usuário para usuários do Enterprise Voice ou usuários de conferência discada, o usuário deve receber um plano de discagem. As contas do usuário usarão automaticamente o plano de discagem global ou, se existir, o plano de discagem a nível do site quando você não atribuir explicitamente um plano de discagem por usuário existente. Se quiser usar o plano de discagem global ou de site para todos os usuários habilitados para o Enterprise Voice, você pode ignorar esta seção.

<div>

## <a name="to-assign-a-dial-plan"></a>Para atribuir um plano de discagem

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Para atribuir um plano de discagem específico do usuário, execute o seguinte no prompt de comando:
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    Por exemplo:
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    Neste exemplo, o usuário com o nome de exibição Bob Kelly recebe o plano de discagem do usuário com o nome **chamado dialplanjapan**.

Para obter detalhes sobre como atribuir um plano de discagem do usuário ou sobre a execução do cmdlet **Grant-CsDialPlan** , consulte a documentação do [Shell de gerenciamento do Lync Server 2013](lync-server-2013-lync-server-management-shell.md) .

</div>

</div>

<div>

## <a name="see-also"></a>Confira Também


[Desabilitar um usuário para o Enterprise Voice no Lync Server 2013](lync-server-2013-disable-a-user-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

