---
title: 'Lync Server 2013: criar ou modificar uma política de mobilidade'
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
ms.openlocfilehash: 3f64e74b389b268027e06b2f4103b0c828c5be6f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a>Criar ou modificar uma política de mobilidade no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-23_

Você pode criar ou modificar a política de mobilidade para permitir que os usuários móveis usem dispositivos móveis compatíveis para a funcionalidade do Lync, como mensagens instantâneas (IM), presença e contatos. Você pode criar ou modificar políticas de mobilidade no painel de controle do Lync Server 2013 ou no Shell de gerenciamento do Lync Server 2013

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a>Para criar uma política de mobilidade com o painel de controle do Lync Server

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **clientes**e, em seguida, clique no botão de navegação da **política de mobilidade** .

4.  Na página **política de mobilidade** , clique em **novo**e siga um destes procedimentos:
    
    1.  Para criar uma política de mobilidade do site, clique em **política do site**, clique em um site, clique em **OK**, examine as configurações padrão e, se quiser, faça as alterações.
    
    2.  Para criar uma política de mobilidade de usuário, clique em **política de usuário**, digite um nome, examine as configurações padrão e, se quiser, faça as alterações.

5.  Clique em **Confirmar**.

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a>Para modificar uma política de mobilidade com o painel de controle do Lync Server

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **clientes**e, em seguida, clique no botão de navegação da **política de mobilidade** .

4.  Na página **política de mobilidade** , clique em uma das políticas de mobilidade existentes.

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  Edite qualquer uma das configurações.

7.  Clique em **Confirmar**.

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a>Criando políticas de acesso externo usando cmdlets do Windows PowerShell

Você pode criar políticas de mobilidade (no escopo do site ou no escopo por usuário) usando o Windows PowerShell e o cmdlet **New-CsMobilityPolicy** . Além disso, você pode usar o cmdlet **set-CsMobilityPolicy** para modificar qualquer uma de suas políticas existentes, incluindo a política global. Esses cmdlets podem ser executados no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a>Para criar uma política de mobilidade no escopo do site

  - Este comando cria uma nova política de mobilidade para o site de Redmond:
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    Como nenhum parâmetro (que não seja o parâmetro Identity obrigatório) foi especificado no comando anterior, as políticas usarão os valores padrão para todas as suas propriedades.

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a>Para criar uma política de mobilidade no escopo por usuário

  - Para criar uma política de mobilidade no escopo por usuário, especifique uma identidade exclusiva para a política:
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a>Para alterar um único valor de propriedade ao criar uma política de mobilidade

  - Para criar políticas que usam valores de propriedades diferentes, inclua o parâmetro apropriado e o valor do parâmetro. Por exemplo, esse comando cria uma política de mobilidade que desabilita a chamada por meio do trabalho:
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a>Para alterar vários valores de propriedade ao criar uma política de mobilidade

  - Vários valores de propriedade podem ser modificados incluindo vários parâmetros. Por exemplo, esse comando cria uma política que desabilita a mobilidade e a chamada por meio do trabalho:
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

Para obter detalhes, consulte o tópico da ajuda para os cmdlets [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) e [set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) .

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

