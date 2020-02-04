---
title: 'Lync Server 2013: executar casos de teste de roteamento de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run voice routing test cases
ms:assetid: fb4d32df-b9ea-4944-8cd7-a6102c78c465
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413068(v=OCS.15)
ms:contentKeyID: 48185948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14f2df8a04c5efbf8c62bc4e17bbdd156913daae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a>Executar casos de teste de roteamento de voz no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-24_

Você pode executar todos os casos de teste em seu pacote de casos de teste de roteamento de voz, ou pode executar um ou mais casos de teste selecionados.

<div>

## <a name="to-run-all-voice-routing-test-cases"></a>Para executar todos os casos de teste de roteamento de voz

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Roteamento de voz** e, em seguida, clique em **testar roteamento de voz**.

4.  Na página **testar roteamento de voz** , clique em **ação** e, em seguida, clique em **executar tudo**.
    
    O status de aprovação ou falha de cada caso de teste é mostrado na coluna **pass/fail** . Se um caso de teste ainda não foi executado, N/d é mostrado na coluna **pass/fail** .

5.  Adicionais Para ver os resultados detalhados de cada caso de teste, clique duas vezes no nome do caso de teste. Os resultados são mostrados na área sombreada no lado direito da página **Editar caso de teste** :
    
    1.  **Resultado do teste:** Status geral de aprovação ou falha da execução do caso de teste.
    
    2.  **Regra de normalização:** A primeira regra de normalização no plano de discagem selecionada para este caso de teste que corresponda ao número discado (o valor no campo **número a ser testado** ).
    
    3.  **Número normalizado:** O valor do número discado após a regra de normalização o converteu.
    
    4.  **Uso da primeira PSTN:** O primeiro registro de uso de rede telefônica pública comutada (PSTN) na política de voz selecionada para este caso de teste que corresponda ao número discado.
    
    5.  **Primeira rota:** A primeira rota de voz no primeiro registro de uso PSTN que corresponde ao número discado.
        
        <div>
        

        > [!NOTE]  
        > O <STRONG>registro de uso PSTN esperado</STRONG> e os campos de <STRONG>rota esperada</STRONG> são opcionais na configuração de caso de teste de roteamento de voz. Se o caso de teste não especificar esses valores, o campo correspondente nos resultados do teste estará vazio.

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a>Para executar um ou mais casos de teste de roteamento de voz selecionado

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Roteamento de voz**e, em seguida, clique em **testar roteamento de voz**.

4.  Na página **testar roteamento de voz** , clique nos nomes dos casos de teste que você deseja executar.

5.  No menu **ação** , clique em **executar selecionado**.
    
    O status de aprovação ou falha de cada caso de teste é mostrado na coluna **pass/fail** . Se um caso de teste ainda não foi executado, N/d é mostrado na coluna **pass/fail** .

6.  Adicionais Para ver os resultados detalhados de cada caso de teste, clique duas vezes no nome do caso de teste. Os resultados são mostrados na área sombreada no lado direito da página **Editar caso de teste** :
    
    1.  **Resultado do teste:** Status geral de aprovação ou falha da execução do caso de teste.
    
    2.  **Regra de normalização:** A primeira regra de normalização no plano de discagem selecionada para este caso de teste que corresponda ao número discado (o valor no campo **número a ser testado** ).
    
    3.  **Número normalizado:** O valor do número discado após a regra de normalização o converteu.
    
    4.  **Uso da primeira PSTN:** O primeiro registro de uso PSTN na política de voz selecionada para este caso de teste que corresponda ao número discado.
    
    5.  **Primeira rota:** A primeira rota de voz no primeiro registro de uso PSTN que corresponde ao número discado.
        
        <div>
        

        > [!NOTE]  
        > O <STRONG>registro de uso PSTN esperado</STRONG> e os campos de <STRONG>rota esperada</STRONG> são opcionais na configuração de caso de teste de roteamento de voz. Se o caso de teste não especificar esses valores, o campo correspondente nos resultados do teste estará vazio.

        
        </div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Testar roteamento de voz no Lync Server 2013](lync-server-2013-test-voice-routing.md)  
[Executando testes de roteamento de voz no Lync Server 2013](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

