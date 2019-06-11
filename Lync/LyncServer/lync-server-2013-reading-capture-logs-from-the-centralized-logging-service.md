---
title: 'Lync Server 2013: lendo logs de captura do serviço de log centralizado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reading capture logs from the Centralized Logging Service
ms:assetid: c86ccf61-d86f-4ebd-b8d1-984a1b73005d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721879(v=OCS.15)
ms:contentKeyID: 49733813
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55bfeaa5bc9a2e89d8c52529c5d05ae7e3ee8feb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reading-capture-logs-from-the-centralized-logging-service-in-lync-server-2013"></a>Ler logs de captura do serviço de log centralizado no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2016-12-28_

Você percebe o verdadeiro benefício do serviço de registro centralizado depois de executar a pesquisa e tem um arquivo que pode ser usado para rastrear um problema relatado. Há várias maneiras de ler o arquivo. O arquivo de saída está em um formato de texto padrão e você pode usar o notepad. exe ou qualquer outro programa que permita a abertura e leitura de um arquivo de texto. Para arquivos maiores e problemas mais complexos, você pode usar uma ferramenta como o Snooper. exe projetado para ler e analisar a saída de log do serviço de log centralizado. O Snooper está incluído nas ferramentas de depuração do Lync Server 2013 disponíveis como um download separado. Você pode baixar as ferramentas de depuração do Lync Server 2013 [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)aqui:. Quando você instala as ferramentas de depuração do Lync Server 2013, pequenos atalhos e itens de menu não são criados. Depois de instalar as ferramentas de depuração do Lync Server 2013, abra o Windows Explorer, uma janela de linha de comando ou o Shell de gerenciamento do Lync Server e vá para o diretório\\(local\\padrão) C:\\arquivos de programas Microsoft Lync Server 2013 ferramentas de depuração. Clique duas vezes em Espionador. exe ou digite Snooper. exe e pressione ENTER se estiver usando a linha de comando ou o Shell de gerenciamento do Lync Server.

<div>


> [!IMPORTANT]  
> A intenção deste tópico não é detalhar e discutir técnicas de resolução de problemas. A resolução de problemas e os processos relacionados é um assunto complexo. Para obter detalhes sobre como solucionar problemas de noções básicas e solucionar problemas de cargas de trabalho específicas, consulte o <A href="http://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>Microsoft Lync Server 2010 Resource Kit book. Os processos e procedimentos ainda se aplicam ao Lync Server 2013.



</div>

O Lync Server 2013 apresenta uma versão atualizada do Espionador que inclui alguns recursos novos. A captura de tela a seguir mostra a versão do Espionador do Office Communications Server 2007.

![Versão do Office communications 2007 do espionador.] (images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Versão do Office communications 2007 do espionador.")

A captura de tela a seguir mostra a nova versão do Espionador incluída nas ferramentas de depuração do Lync Server 2013.

![Versão do espionador do Lync Server 2013.] (images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Versão do espionador do Lync Server 2013.")

A captura de tela a seguir mostra a barra de ferramentas com funções usadas com frequência.

![Barra de ferramentas do espionador 2013.] (images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Barra de ferramentas do espionador 2013.")

Além disso, o recurso mais recente que adiciona valor é o modo de exibição de diagrama de fluxograma (fluxo de chamadas). Selecione um fluxo de mensagens na guia **mensagem** e clique no botão **fluxo de chamadas** . Ao passar pelas mensagens, o diagrama de fluxo de chamadas é atualizado com novos dados.

![Diagrama de fluxo de chamadas do espionador 2013.] (images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Diagrama de fluxo de chamadas do espionador 2013.")

Você pode passar o mouse sobre o modo de exibição de diagrama e obter detalhes sobre as mensagens e o conteúdo dos fluxos e mensagens, bem como os elementos do servidor. Clique em qualquer seta de fluxo de chamadas para ir até a mensagem no modo de exibição mensagens.

![Detalhes da mensagem do diagrama de fluxo de chamadas.] (images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Detalhes da mensagem do diagrama de fluxo de chamadas.")

<div>

## <a name="to-open-a-log-file-in-snooper"></a>Para abrir um arquivo de log no Snooper

1.  Para usar o Snooper e abrir arquivos de log, você precisará de acesso de leitura aos arquivos de log. Para usar o Snooper e acessar os arquivos de log, você deve ser membro dos grupos de segurança RBAC CsAdministrator ou CsServerAdministrator ou uma função RBAC personalizada que contém um desses dois grupos.

2.  Após a instalação das ferramentas de depuração do Lync Server (LyncDebugTools. msi), altere diretório para o local de Snooper. exe usando o Windows Explorer ou a partir da linha de comando. Por padrão, as ferramentas de depuração estão localizadas em\\C:\\arquivos de programa ferramentas\\de depuração do Microsoft Lync Server 2013. Clique duas vezes ou execute Snooper.exe.

3.  Após o Snooper estar aberto, clique com o botão direito em **Arquivo**, clique em **Abrir arquivo**, encontre seus arquivos de registro, selecione um arquivo na caixa de diálogo **Abrir** e clique em **Abrir**.

4.  As mensagens de **Rastreamento** do arquivo de log são exibidas na guia **Rastreamento**. Clique na guia **Mensagens** para exibir o conteúdo da mensagem dos rastreamentos coletados.

</div>

<div>

## <a name="to-display-a-call-flow-diagram"></a>Para exibir um fluxograma da chamada

1.  Para usar o Snooper e abrir arquivos de log, você precisa de acesso de leitura dos arquivos de log. Para usar o Snooper e acessar os arquivos de log, você precisará ser um membro dos grupos de segurança RBAC CsAdministrator ou CsServerAdministrator ou uma função RBAC personalizada que contém um destes dois grupos.

2.  Abra um arquivo de log e clique na guia **Mensagens**, selecione uma conversa na exibição de mensagens ou selecione um componente de rastreamento na guia **Rastreamento**.

3.  Clique em **Fluxo de chamadas**.
    
    <div>
    

    > [!NOTE]  
    > Se você clicar em uma mensagem ou rastreamento que não faz parte do fluxo de chamadas, o diagrama não aparecerá e uma mensagem de status aparece na parte inferior do Snooper dizendo “Esta mensagem não é elegível para fluxo de chamadas”. Escolha outra mensagem ou rastreamento e o fluxo de chamadas aparecerá se a mensagem ou o rastreamento faz parte de um fluxo de chamadas.

    
    </div>

4.  Mova pelas Mensagens ou linhas de Rastreamento e observe se o fluxograma de chamada atualiza ou muda para exibir um novo diagrama.

5.  Passe sobre os elementos para obter informações sobre mensagens de chamada, pontos de extremidade e outros componentes.

</div>

</div>

<span> </span>

</div>

</div>

</div>

