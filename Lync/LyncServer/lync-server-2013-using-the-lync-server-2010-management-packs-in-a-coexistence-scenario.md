---
title: Usando os pacotes de gerenciamento do Lync Server 2010 em um cenário de coexistência
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2010 management packs in a coexistence scenario
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205078(v=OCS.15)
ms:contentKeyID: 48184772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 264cd8f1495840eb6dd86879f279110cd4de4784
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743881"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a>Usando os pacotes de gerenciamento do Lync Server 2010 em um cenário de coexistência

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-22_

Muitos clientes adotam um programa de distribuição dentro de suas empresas, em que os usuários migram progressivamente do Microsoft Lync Server 2010 para o Lync Server 2013. Os administradores nessas empresas se preocupam em monitorar as duas versões do Lync Server para ajudar a garantir que todos os seus usuários finais tenham a melhor experiência de comunicação possível. Para esse cenário, o pacote de gerenciamento do Lync Server 2013 dá suporte a um caminho de migração lado a lado com o pacote de gerenciamento do Lync Server 2010.

No Lync Server 2010, os computadores do Lync Server foram descobertos por meio do documento de topologia armazenado com o repositório de gerenciamento central. Nesta configuração, um único computador pode reportar a existência de todos os outros computadores do Lync Server.

Os pacotes de gerenciamento do Lync Server 2013 agora usam a descoberta em nível de máquina em vez do mecanismo de descoberta central usado no Lync Server 2010. Isso significa que cada agente do System Center essencialmente descobre e relata sua existência ao System Center Operations Manager. O uso da descoberta no nível da máquina simplifica a administração da infraestrutura do sistema central e também permite diferentes versões dos pacotes de gerenciamento do Lync Server (por exemplo, pacotes de gerenciamento do Lync Server 2010 e pacotes de gerenciamento do Lync Server 2013) para coexistir mais facilmente.

Para dar suporte a essa migração, primeiro você precisará atualizar o monitoramento existente do Lync Server 2010 para evitar lacunas na cobertura. Para fazer isso, elege um computador existente do Lync Server 2010 para atender ao script de descoberta central do servidor do Lync 2010 antes de atualizar seu repositório de gerenciamento central para o Lync Server 2013. Este é um processo de quatro etapas:

1.  Atualize os pacotes de gerenciamento do Lync Server 2010 para a atualização cumulativa 7.

2.  Instrua um computador com o Lync Server 2010 para executar o script de descoberta central.

3.  Substitua o candidato de descoberta central no pacote de gerenciamento do Microsoft Lync Server 2010.

4.  Verifique se o novo candidato de descoberta central foi descoberto.

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a>Como instruir um computador com o Lync Server 2010 para executar o script de descoberta central

Para indicar um computador que não seja do repositório de gerenciamento central (por exemplo, um servidor front-end do Lync Server) para manipular a descoberta central, você precisará criar a seguinte chave do registro no servidor do repositório de gerenciamento não central:

Software\\\\HKLM CentralDiscoveryCandidate\\integridade\\\\da comunicação em tempo real da Microsoft

Você pode criar essa chave do registro completando o seguinte procedimento:

1.  Clique em **Iniciar** e em **executar**.

2.  Na caixa de diálogo **executar** , digite **regedit** e pressione Enter.

3.  No editor do registro, expanda **HKEY\_\_local Machine**, expanda **software**, expanda **Microsoft**e, em seguida, expanda **comunicações em tempo real**.

4.  Clique com o botão direito do mouse em **integridade**, clique em **novo**e clique em **chave**. Se a chave de **integridade** não existir, clique com o botão direito do mouse em **comunicações em tempo real**, aponte para **novo**e clique em **tecla**. Quando a nova chave for criada, digite Health e pressione ENTER.
    
    Após a criação da nova chave, digite **CentralDiscoveryCandidate** e pressione ENTER para renomear a chave.

Pode levar o computador várias horas para que essa alteração seja retomada. Para fazer com que a alteração entre em vigor imediatamente, pare e reinicie o serviço do agente de integridade. Para reiniciar o serviço do agente de integridade, conclua o procedimento a seguir no computador do Lync Server 2010:

1.  Clique em **Iniciar**, **em todos os programas**, em **acessórios**, clique com o botão direito do mouse em **prompt de comando**e, em seguida, clique em **Executar como administrador**.

2.  Na janela do console, digite o seguinte comando e pressione ENTER:
    
        Net stop HealthService

3.  Você verá uma mensagem que informa que "o serviço de gerenciamento do System Center está sendo interrompido", seguido por uma segunda mensagem que informa que o serviço foi interrompido. Depois que o serviço for interrompido, você poderá reiniciá-lo digitando o seguinte comando e pressionando ENTER:
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a>Substituindo o candidato à descoberta central no pacote de gerenciamento do Lync Server 2010

Depois de instruir um computador do Lync Server 2010 a ser relatado nos computadores do Lync Server 2010, você precisará informar o pacote de gerenciamento do Lync Server 2010 sobre essa alteração também. Para fazer isso, será necessário criar uma substituição no pacote de gerenciamento. Isso pode ser feito completando o seguinte procedimento:

1.  No console do Operations Manager, clique em **criação**.

2.  Na guia criação de páginas, expanda **objetos do pacote de gerenciamento**, clique em descobertas de **objeto**e, em seguida, clique em **escopo**.

3.  Na caixa de diálogo **escopo de objetos do pacote de gerenciamento** , selecione o item com o candidato da **descoberta ls** de destino e clique em **OK**. Observe que o candidato da descoberta de LS será exibido apenas se você tiver instalado o pacote de gerenciamento do Lync Server 2010.

4.  No console do Operations Manager, clique com o botão direito do mouse em **candidato à descoberta ls**, aponte para **substituições**, aponte para **substituir a descoberta de objeto**e clique em **para todos os objetos da classe: candidato à descoberta de ls**.

5.  Na caixa de diálogo **substituir Propriedades** , marque a caixa de seleção **substituir** ao lado da **descoberta central do parâmetro WatcherNode FQDN**. Digite o nome de domínio totalmente qualificado do computador do Lync Server 2010 nas caixas **substituir valor** e **valor efetivo** . Marque a caixa de seleção **imposto** e clique em **OK**.

Depois de criar a substituição, você precisará reiniciar o serviço de integridade no servidor de gerenciamento raiz. Para reiniciar o serviço de integridade, conclua o procedimento a seguir no servidor de gerenciamento raiz:

1.  Clique em **Iniciar**, **em todos os programas**, em **acessórios**, clique com o botão direito do mouse em **prompt de comando**e, em seguida, clique em **Executar como administrador**.

2.  Na janela do console, digite o seguinte comando e pressione ENTER:
    
        Net stop HealthService

3.  Você verá uma mensagem informando que "o serviço de gerenciamento do System Center está sendo interrompido", seguido por uma segunda mensagem que informa que o serviço foi interrompido. Depois que o serviço for interrompido, você poderá reiniciá-lo digitando o seguinte comando e pressionando ENTER:
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a>Verificando se o novo candidato de descoberta central foi descoberto

A etapa final antes da atualização do repositório de gerenciamento central é verificar se o novo candidato de descoberta central foi descoberto pelo pacote de gerenciamento do Lync Server 2010. Para fazer isso, abra o console do Operations Manager e, em seguida, clique em monitoramento. Na guia monitoramento, expanda **integridade do Microsoft Lync Server 2010**, expanda **descoberta de topologia**e clique em **modo de exibição estado de descoberta**. Verifique se uma linha na tela tem um **caminho** que lista o nome de domínio totalmente qualificado do candidato à descoberta central. Você também deve verificar se o estado do computador é reportado como **íntegro**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

