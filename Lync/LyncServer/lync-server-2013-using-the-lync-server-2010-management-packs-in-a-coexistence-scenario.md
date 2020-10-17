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
ms.openlocfilehash: bb614726458f2cf9c77bdfe740ddb13d99d54f2f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529918"
---
# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a>Usando os pacotes de gerenciamento do Lync Server 2010 em um cenário de coexistência

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-22_

Muitos clientes adotam um programa de distribuição dentro de suas empresas nas quais os usuários são migrados progressivamente do Microsoft Lync Server 2010 para o Lync Server 2013. Os administradores dessas empresas se preocupam em monitorar as duas versões do Lync Server para ajudar a garantir que todos os usuários finais estejam obtendo a melhor experiência de comunicação possível. Para este cenário, o pacote de gerenciamento do Lync Server 2013 oferece suporte a um caminho de migração lado a lado com o pacote de gerenciamento do Lync Server 2010.

No Lync Server 2010, os computadores do Lync Server foram detectados pelo documento de topologia armazenado com o repositório de gerenciamento central. Nessa configuração, um único computador reportaria a existência de todos os outros computadores do Lync Server.

Os pacotes de gerenciamento do Lync Server 2013 agora usam a descoberta no nível de máquina em vez do mecanismo de descoberta central usado no Lync Server 2010. Isso significa que cada agente do System Center, descobre essencialmente a si mesmo e relata sua existência ao System Center Operations Manager. O uso da descoberta no nível da máquina simplifica a administração da infraestrutura do System Center e também permite diferentes versões dos pacotes de gerenciamento do Lync Server (por exemplo, pacotes de gerenciamento do Lync Server 2010 e pacotes de gerenciamento do Lync Server 2013) para coexistir com mais facilidade.

Para dar suporte a essa migração, primeiro você precisará atualizar seu monitoramento existente do Lync Server 2010 para evitar lacunas de cobertura. Para fazer isso, elege um computador existente do Lync Server 2010 para atender ao script de descoberta central do Lync Server 2010 antes de atualizar seu repositório de gerenciamento central para o Lync Server 2013. Este é um processo em quatro etapas:

1.  Atualize os pacotes de gerenciamento do Lync Server 2010 para a atualização cumulativa 7.

2.  Instrua um computador do Lync Server 2010 para executar o script de descoberta central.

3.  Substitua o candidato de descoberta central no pacote de gerenciamento do Microsoft Lync Server 2010.

4.  Verifique se o novo Candidato a Descoberta Central foi descoberto.

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a>Instrua um computador com Lync Server 2010 para executar o script de Descoberta Central

Para indicar um computador do repositório de gerenciamento não central (por exemplo, um servidor front-end do Lync Server) para lidar com a descoberta central, você precisará criar a seguinte chave do registro no servidor do repositório de gerenciamento não central:

\\CentralDiscoveryCandidate de \\ \\ integridade de comunicação em tempo real da Microsoft \\ \\

Você pode instalar criar essa chave de registro concluindo o seguinte procedimento:

1.  Clique em **Iniciar** e depois em **Executar**.

2.  Na caixa de diálogo **Executar**, digite **regedit** e pressione ENTER.

3.  No editor do registro, expanda ** \_ \_ máquina local de hKey**, expanda **software**, expanda **Microsoft**e, em seguida, expanda **comunicação em tempo real**.

4.  Com o botão direito em **Integridade**, clique em **Novo**, e depois em **Chave**. Se a chave **Integridade** não existir, clique com o botão direito em **Comunicações em tempo real**, aponte para **Novo**, e depois clique em **Chave**. Quando a nova chave for criada, digite Integridade, e depois pressione ENTER.
    
    Depois que a nova chave for criada, digite **CentralDiscoveryCandidate** e pressione ENTER para renomear a chave.

Pode levar algumas horas para que o computador obtenha essa alteração. Para atualizar essas configurações imediatamente, pare e em seguida reinicie o serviço Agente de Integridade. Para reiniciar o serviço do agente de integridade, conclua o procedimento a seguir no computador do Lync Server 2010:

1.  Clique em **Iniciar**, **Todos os Programas**, **Acessórios**, clique o botão direito no **Prompt de comando**, e depois clique em **Executar como administrador**.

2.  Na janela do console, digite o seguinte comando e pressione ENTER.
    
        Net stop HealthService

3.  Você verá uma mensagem que diz "O serviço de Gerenciamento do 	Gerenciamento do System Center está sendo interrompido", seguida por uma segunda mensagem que diz que o serviço foi interrompido. Após a interrupção do serviço, você pode reiniciá-lo digitando o seguinte comando e pressionando ENTER:
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a>Substituição do Candidato a Descoberta Central no Pacote de Gerenciamento do Lync Server 2010

Depois de instruir um computador do Lync Server 2010 para relatar nos computadores do Lync Server 2010, você precisará informar o pacote de gerenciamento do Lync Server 2010 sobre essa alteração também. Para fazer isso, será necessário criar uma substituição no Pacote de Gerenciamento. Isso pode ser feito realizando o procedimento a seguir:

1.  No console do Operations Manager, clique em **Criação**.

2.  Na guia Criação, expanda **Objetos do Pacote de Gerenciamento**, clique em **Descobertas de Objeto**, e depois em **Escopo**.

3.  Na caixa de diálogo **Delimitar Objetos do Pacote de Gerenciamento**, selecione o item com o **Candidato à descoberta LS** do alvo e depois clique em **OK**. Observe que o candidato à descoberta de LS aparecerá somente se você tiver instalado o pacote de gerenciamento do Lync Server 2010.

4.  No console do Operations Manager, clique com o botão direito em **Candidato à descoberta LS**, aponte para **Substituições**, aponte para **Substituir a Descoberta de Objeto**, e clique em **Para todos os objetos da classe: Candidato à descoberta LS**.

5.  Na caixa de diálogo **Substituir propriedades**, marque a caixa de seleção **Substituir** ao lado do parâmetro **WatcherNode Fqdn da Descoberta Central**. Digite o nome de domínio totalmente qualificado do computador do Lync Server 2010 nas caixas **valor de substituição** e **valor efetivo** . Marque a caixa de seleção **Imposto** e clique em **OK**.

Após criar a substituição, será necessário reiniciar o serviço de integridade no Servidor de Gerenciamento Raiz. Para reiniciar o serviço Agente de Integridade, siga o procedimento a seguir no Servidor de Gerenciamento Raiz:

1.  Clique em **Iniciar**, **Todos os Programas**, **Acessórios**, clique o botão direito no **Prompt de comando**, e depois clique em **Executar como administrador**.

2.  Na janela do console, digite o seguinte comando e pressione ENTER:
    
        Net stop HealthService

3.  Você verá uma mensagem que diz "O serviço de Gerenciamento do 	Gerenciamento do System Center está sendo interrompido", seguida por uma segunda mensagem que diz que o serviço foi interrompido. Após a interrupção do serviço, você poderá reiniciá-lo digitando o seguinte comando e pressionando ENTER:
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a>Verificação se o novo Candidato a Descoberta Central foi descoberto.

A etapa final antes de atualizar o repositório de gerenciamento central é verificar se o novo candidato de descoberta central foi descoberto pelo pacote de gerenciamento do Lync Server 2010. Para isso, abra o console do Operations Manager e clique em Monitoramento. Na guia Monitoramento, expanda **Integridade do Microsoft Lync Server 2010**, expanda **Descoberta de topologia** e depois clique em **Exibição do estado de descoberta**. Verifique se uma linha na exibição tem o **Caminho** que lista o nome de domínio totalmente qualificado do candidato à descoberta central. Você também deve verificar se o estado do computador é relatado como **Íntegro**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

