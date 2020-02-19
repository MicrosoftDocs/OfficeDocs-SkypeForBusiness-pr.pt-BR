---
title: 'Lync Server 2013: lendo logs de captura do serviço de registro em log centralizado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reading capture logs from the Centralized Logging Service
ms:assetid: c86ccf61-d86f-4ebd-b8d1-984a1b73005d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721879(v=OCS.15)
ms:contentKeyID: 49733813
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebb1ec3ebde4f1277d6304190aceafa2e0fe2884
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138872"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reading-capture-logs-from-the-centralized-logging-service-in-lync-server-2013"></a>Ler logs de captura do serviço de registro em log centralizado no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2016-12-28_

Você percebe o real benefício do serviço de registro em log centralizado após a execução da pesquisa e tem um arquivo que pode ser usado para rastrear um problema relatado. Existe um número de formas que você pode ler o arquivo. O arquivo de resultado está em um formato de texto padrão e você pode usar Notepad.exe ou qualquer outro programa que permitirá abrir e ler um arquivo de texto. Para arquivos maiores e problemas mais complexos, você poderia usar uma ferramenta como o Snooper. exe, projetado para ler e analisar a saída de log do serviço de registro em log centralizado. O Snooper é incluído com as Ferramentas de Depuração do Lync Server 2013 disponíveis como um download separado. Você pode baixar as ferramentas de depuração do Lync Server 2013 [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)aqui:. Quando você instala as ferramentas de depuração do Lync Server 2013, atalhos curtos e itens de menu não são criados. Após a instalação das ferramentas de depuração do Lync Server 2013, abra o Windows Explorer, uma janela de linha de comando ou o Shell de gerenciamento do Lync Server e vá para o diretório\\(local\\padrão) C:\\arquivos de programa Microsoft Lync Server 2013 ferramentas de depuração. Clique duas vezes em Snooper. exe ou digite Snooper. exe e pressione ENTER se estiver usando a linha de comando ou o Shell de gerenciamento do Lync Server.

<div>


> [!IMPORTANT]  
> A intenção deste tópico não é detalhar e discutir técnicas de resolução de problemas. A resolução de problemas e os processos relacionados é um assunto complexo. Para obter detalhes sobre como solucionar problemas básicos e solucionar problemas de cargas de trabalho específicas, consulte o Microsoft Lync <A href="https://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>Server 2010 Resource Kit Book em. Os processos e procedimentos ainda se aplicam ao Lync Server 2013.



</div>

O Lync Server 2013 introduz uma versão atualizada do Snooper que inclui alguns recursos novos. A captura de tela a seguir mostra a versão do Snooper do Office Communications Server 2007.

![Versão do Office Communications 2007 do Snooper.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Versão do Office Communications 2007 do Snooper.")

A captura de tela a seguir mostra a nova versão do Snooper incluída nas ferramentas de depuração do Lync Server 2013.

![Lync Server 2013 versão do Snooper.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 versão do Snooper.")

A tela a seguir mostra a barra de ferramentas com funções usadas frequentemente.

![Barra de ferramentas do Snooper 2013.](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Barra de ferramentas do Snooper 2013.")

E, o novo recurso que adiciona valor é a exibição do Fluxograma (fluxo de chamadas). Você seleciona um fluxo de mensagens na guia **Mensagem** e clica no botão **Fluxo de chamada**. Conforme você passa pelas mensagens, o fluxograma de chamada é atualizado com novos dados.

![Diagrama de fluxo de chamadas 2013 do Snooper.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Diagrama de fluxo de chamadas 2013 do Snooper.")

É possível passar sobre a exibição do diagrama e obter detalhes sobre a mensagem e o conteúdo de fluxos e mensagens, assim como os elementos do servidor. Clique em qualquer seta do fluxo de chamadas para ir para a mensagem na exibição de Mensagens.

![Detalhes da mensagem do diagrama de fluxo de chamadas.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Detalhes da mensagem do diagrama de fluxo de chamadas.")

<div>

## <a name="to-open-a-log-file-in-snooper"></a>Para abrir um arquivo de log no Snooper

1.  Para usar o Snooper e abrir arquivos de log, você precisará de acesso de leitura aos arquivos de log. Para usar o Snooper e acessar os arquivos de log, você deve ser membro dos grupos de segurança RBAC CsAdministrator ou CsServerAdministrator ou uma função RBAC personalizada que contém um destes dois grupos.

2.  Após a instalação das ferramentas de depuração do Lync Server (LyncDebugTools. msi), altere o diretório para o local de Snooper. exe usando o Windows Explorer ou a partir da linha de comando. Por padrão, as ferramentas de depuração estão localizadas em\\C:\\arquivos de programa ferramentas\\de depuração do Microsoft Lync Server 2013. Clique duas vezes ou execute Snooper.exe.

3.  Após o Snooper estar aberto, clique com o botão direito em **Arquivo**, clique em **Abrir arquivo**, encontre seus arquivos de log, selecione um arquivo na caixa de diálogo **Abrir** e clique em **Abrir**.

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

