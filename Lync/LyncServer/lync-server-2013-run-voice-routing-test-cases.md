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
ms.openlocfilehash: df0a5ea6da9fad7f6a7e242bb522c493962fc603
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050773"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a>Executar casos de teste de roteamento de voz no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-24_

Você pode executar todos os casos de teste no seu pacote de casos de teste de roteamento de voz ou pode executar um ou mais casos de teste selecionados.

<div>

## <a name="to-run-all-voice-routing-test-cases"></a>Para executar todos os casos de teste de roteamento de voz

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Roteamento de voz** e em **Testar roteamento de voz**.

4.  Na página **Testar roteamento de voz**, clique em **Ação ** e em **Executar todos**.
    
    O status de aprovação ou reprovação de cada caso de teste é exibido na coluna **Aprovado/reprovado**. Se um caso de teste ainda não foi executado, N/D é exibido na coluna **Aprovado/reprovado**.

5.  (Opcional) Para ver os resultados detalhados para cada caso de teste, clique duas vezes no nome do caso de teste. Os resultados são exibidos na área acinzentada no lado direito da página **Editar caso de teste**:
    
    1.  **Resultado do teste:** Status de aprovação geral ou de falha da execução do caso de teste.
    
    2.  **Regra de normalização:** A primeira regra de normalização no plano de discagem selecionado para este caso de teste que corresponde ao número discado (o valor no campo **número para teste** ).
    
    3.  **Número normalizado:** O valor do número discado após a regra de normalização a converteu.
    
    4.  **Primeiro uso de PSTN:** O primeiro registro de uso de PSTN (rede telefônica pública comutada) na política de voz selecionada para este caso de teste que corresponde ao número discado.
    
    5.  **Primeiro roteamento:** A primeira rota de voz no primeiro registro de uso de PSTN que corresponde ao número discado.
        
        <div>
        

        > [!NOTE]  
        > Os campos <STRONG>Registro de uso PSTN esperado</STRONG> e <STRONG>Roteamento esperado</STRONG> são opcionais na configuração do caso de teste de roteamento de voz. Se o caso de teste não especificar estes valores, o campo correspondente nos resultados de teste estarão vazios.

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a>Para executar um ou mais casos de teste de roteamento de voz selecionados

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Roteamento de Voz** e em **Testar roteamento de voz**.

4.  Na página **Testar roteamento de voz **, clique nos nomes dos casos de teste que você deseja executar.

5.  No menu **Ação **, clique em **Executar selecionado**.
    
    O status de aprovação ou reprovação de cada caso de teste é exibido na coluna **Aprovado/reprovado**. Se um caso de teste ainda não foi executado, N/D é exibido na coluna **Aprovado/reprovado**.

6.  (Opcional) Para ver os resultados detalhados para cada caso de teste, clique duas vezes no nome do caso de teste. Os resultados são exibidos na área acinzentada no lado direito da página **Editar caso de teste**:
    
    1.  **Resultado do teste:** Status de aprovação geral ou de falha da execução do caso de teste.
    
    2.  **Regra de normalização:** A primeira regra de normalização no plano de discagem selecionado para este caso de teste que corresponde ao número discado (o valor no campo **número para teste** ).
    
    3.  **Número normalizado:** O valor do número discado após a regra de normalização a converteu.
    
    4.  **Primeiro uso de PSTN:** O primeiro registro de uso de PSTN na política de voz selecionada para este caso de teste que corresponde ao número discado.
    
    5.  **Primeiro roteamento:** A primeira rota de voz no primeiro registro de uso de PSTN que corresponde ao número discado.
        
        <div>
        

        > [!NOTE]  
        > Os campos <STRONG>Registro de uso PSTN esperado</STRONG> e <STRONG>Roteamento esperado</STRONG> são opcionais na configuração do caso de teste de roteamento de voz. Se o caso de teste não especificar estes valores, o campo correspondente nos resultados de teste estarão vazios.

        
        </div>

</div>

<div>

## <a name="see-also"></a>Confira Também


[Testar roteamento de voz no Lync Server 2013](lync-server-2013-test-voice-routing.md)  
[Executando testes de roteamento de voz no Lync Server 2013](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

