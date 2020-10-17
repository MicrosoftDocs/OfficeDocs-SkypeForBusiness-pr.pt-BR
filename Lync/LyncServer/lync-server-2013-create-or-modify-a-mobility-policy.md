---
title: 'Lync Server 2013: criar ou modificar uma política de mobilidade'
description: 'Lync Server 2013: criar ou modificar uma política de mobilidade.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a mobility policy
ms:assetid: fc2dfea0-2215-440d-9f4b-7c985da29211
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721946(v=OCS.15)
ms:contentKeyID: 49733884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fcf593c568a8ecf1bd6791641affc4076672b250
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566097"
---
# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a>Criar ou modificar uma política de mobilidade no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

Você pode criar ou modificar a política de mobilidade para permitir que usuários móveis usem os dispositivos móveis suportados para a funcionalidade Lync, como mensagens instântaneas (IM), presença e contatos. Você pode criar ou modificar políticas de mobilidade no painel de controle do Lync Server 2013 ou no Shell de gerenciamento do Lync Server 2013

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a>Para criar uma política de mobilidade com o painel de controle do Lync Server

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Clientes** e no botão de navegação **Política de Mobilidade**.

4.  Na página **política de mobilidade** , clique em **novo**e siga um destes procedimentos:
    
    1.  Para criar uma política de mobilidade do site, clique em **Política do Site**, clique em um site e en **OK**; reveja as configurações e faça as mudanças desejadas, se aplicável.
    
    2.  Para criar uma política de mobilidade do usuário, clique em **Política do Usuário**, digite um nome, reveja as configurações e faça as mudanças desejadas, se aplicável.

5.  Clique em **Confirmar**.

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a>Para modificar uma política de mobilidade com o painel de controle do Lync Server

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Clientes** e no botão de navegação **Política de Mobilidade**.

4.  Na página **política de mobilidade** , clique em uma das políticas de mobilidade existentes.

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  Edite as configurações.

7.  Clique em **Confirmar**.

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a>Criar políticas de acesso externo usando cmdlets do Windows PowerShell

Você pode criar políticas de mobilidade (no escopo do site ou no escopo por usuário) usando o Windows PowerShell e o cmdlet **New-CsMobilityPolicy** . Ademais, você pode usar o cmdlet **Set-CsMobilityPolicy** para modificar qualquer política existente, incluindo a política global. Esses cmdlets podem ser executados a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a>Para criar uma política de mobilidade no escopo do site

  - Esse comando cria uma nova política de mobilidade para o site de Redmond:
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    Já que nenhum parâmetro (além do parâmetro obrigatório Identity) foi especificado no comando precedente, as políticas usarão os valores padrão para todas as suas propriedades.

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a>Para criar uma política de mobilidade no escopo por usuário

  - Para criar uma política de mobilidade no escopo por usuário, especifique uma Identidade exclusiva para a política:
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a>Para alterar um único valor de propriedade ao criar uma política de mobilidade

  - Para criar políticas que usam diferentes valores de propriedade, inclua o parâmetro e o valor de parâmetro adequados. Por exemplo, esse comando cria a política de mobilidade que desabilita Chamada via Trabalho:
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a>Para alterar vários valores de propriedade ao criar uma política de mobilidade

  - Valores múltiplos de propriedade podem ser modificados incluindo parâmetros múltiplos. Por exemplo, esse comando cria uma política que desabilita mobilidade e Chamada via Trabalho:
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

Para detalhes, consulte o tópico de ajuda para os cmdlets [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) e [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy).

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurando a política de mobilidade no Lync Server 2013](lync-server-2013-configuring-mobility-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

