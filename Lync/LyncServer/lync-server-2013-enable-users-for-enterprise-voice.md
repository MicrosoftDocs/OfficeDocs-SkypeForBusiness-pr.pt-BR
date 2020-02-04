---
title: 'Lync Server 2013: habilitar usuários do Enterprise Voice'
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
ms.openlocfilehash: 0b851c8807e12456c600b2ca176b0fa5a834f0d5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736011"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-enterprise-voice-in-lync-server-2013"></a>Habilitar usuários para Enterprise Voice no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

Depois de instalar arquivos para um ou mais servidores de mediação, configurar o roteamento de chamadas de saída e, opcionalmente, implantar um ou mais recursos avançados do Enterprise Voice, você pode usar os seguintes procedimentos para permitir que um usuário faça chamadas usando o Enterprise Voice:

<div>


> [!NOTE]  
> Dos procedimentos a seguir, somente o primeiro pode ser executado usando o painel de controle do Lync Server. Para obter os procedimentos restantes, você pode usar apenas o Shell de gerenciamento do Lync Server.



</div>

  - Habilite a conta de usuário do Enterprise Voice.

  - (Opcional) Atribuir a conta de usuário com uma política de voz específica do usuário.

  - (Opcional) Atribuir a conta do usuário com um plano de discagem específico do usuário.

<div>

## <a name="to-enable-a-user-account-for-enterprise-voice"></a>Para habilitar uma conta de usuário para o Enterprise Voice

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Usuários**.

4.  Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.

5.  Na tabela, clique na conta de usuário que você deseja habilitar para o Enterprise Voice.

6.  No menu **Editar**, clique em **Exibir detalhes**.

7.  Na página **Editar usuário do Lync Server** , em **telefonia**, clique em **Enterprise Voice**.

8.  Clique em **URI de linha** e digite um número de telefone único e normalizado (por exemplo, tel:+14255550200).

9.  Clique em **Confirmar**.

Para concluir a habilitação de um usuário para o Enterprise Voice, certifique-se de que o usuário tenha atribuído uma política de voz e um plano de discagem, seja global (atribuído por padrão) ou específico ao usuário.

Por padrão, todos os usuários recebem uma política de voz global e um plano de discagem. Se houver uma política de voz ou um plano de discagem no nível do site no qual a conta de usuário é hospedada, essas políticas do site serão aplicadas automaticamente ao usuário. Para aplicar uma política de voz por usuário ou um plano de discagem a um usuário, você deve executar os cmdlets **Grant-CsVoicePolicy** e **Grant-CsDialPlan** . Para obter detalhes, consulte a documentação do [Shell de gerenciamento do Lync Server 2013](lync-server-2013-lync-server-management-shell.md) .

</div>

<div>

## <a name="voice-policy-assignment"></a>Atribuição de política de voz

Políticas de voz globais e no nível do site são automaticamente atribuídas a todas as contas de usuário habilitadas para o Enterprise Voice. Você também pode criar políticas de voz que se aplicam a usuários ou grupos específicos. Essas políticas por usuário devem ser explicitamente atribuídas aos usuários ou grupos. Se quiser usar a política de voz global ou de site para todos os usuários habilitados para o Enterprise Voice, você poderá ignorar esta seção e continuar a discagem da seção de atribuição de plano posteriormente neste tópico.

<div>

## <a name="to-assign-a-user-specific-voice-policy"></a>Para atribuir uma política de voz específica do usuário

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Para atribuir uma política de voz de usuário existente a um usuário, execute o seguinte no prompt de comando:
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    Por exemplo:
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    Neste exemplo, o usuário com o nome para exibição Bob está atribuído à política de voz com o nome **VoicePolicyJapan**.

Para obter detalhes sobre como atribuir uma política de voz específica do usuário ou sobre como executar o cmdlet **Grant-CsVoicePolicy** , consulte a documentação do [Shell de gerenciamento do Lync Server 2013](lync-server-2013-lync-server-management-shell.md) .

</div>

</div>

<span id="BKMK_DialPlanAssignment"></span>

<div>

## <a name="dial-plan-assignment"></a>Atribuição de plano de discagem

Para concluir a configuração da conta de usuário para usuários do Enterprise Voice ou usuários de conferências discadas, o usuário deve receber um plano de discagem. As contas de usuário usarão automaticamente o plano de discagem global ou, se houver, o plano de discagem no nível do site, quando você não atribui explicitamente um plano de discagem por usuário existente. Se quiser usar o plano global ou de discagem de site para todos os usuários que estão habilitados para o Enterprise Voice, você pode ignorar esta seção.

<div>

## <a name="to-assign-a-dial-plan"></a>Para atribuir um plano de discagem

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Para atribuir um plano de discagem específico do usuário, execute o seguinte no prompt de comando:
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    Por exemplo:
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    Neste exemplo, o usuário com o nome para exibição Bob está atribuído ao plano de discagem do usuário com o nome **DialPlanJapan**.

Para obter detalhes sobre como atribuir um plano de discagem do usuário ou sobre como executar o cmdlet **Grant-CsDialPlan** , consulte a documentação do [Shell de gerenciamento do Lync Server 2013](lync-server-2013-lync-server-management-shell.md) .

</div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Desabilitar um usuário para o Enterprise Voice no Lync Server 2013](lync-server-2013-disable-a-user-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

