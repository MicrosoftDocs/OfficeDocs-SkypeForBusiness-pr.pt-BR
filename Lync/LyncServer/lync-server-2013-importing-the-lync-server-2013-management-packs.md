---
title: 'Lync Server 2013: importando os pacotes de gerenciamento do Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Importing the Lync Server 2013 management packs
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205052(v=OCS.15)
ms:contentKeyID: 48184690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bd5f09d80aa86c9c0f692fbe0e744a445067e74
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="importing-the-lync-server-2013-management-packs"></a>Importando os pacotes de gerenciamento do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-22_

Você pode estender os recursos do System Center Operations Manager Instalando pacotes de gerenciamento — software que determina quais itens o System Center Operations Manager pode monitorar e como esses itens devem ser monitorados e como os alertas devem ser acionados e informação. O Lync Server 2013 inclui dois pacotes de gerenciamento do System Center Operations Manager que oferecem os seguintes recursos:

  - O pacote de gerenciamento de componente e usuário (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) rastreia problemas do Lync Server registrados em logs de eventos, registrados por contadores de desempenho ou registrados nos registros de detalhes da chamada (CDR) ou na qualidade da experiência (QoE) bancos. Para problemas críticos, o System Center Operations Manager pode ser configurado para notificar imediatamente os administradores por email, mensagem instantânea ou mensagens SMS (Short Message Service). O SMS é a tecnlogia usada para enviar mensagens entre celulares.
    
    <div>
    

    > [!NOTE]  
    > Para obter detalhes sobre como configurar a notificação do Operations Manager, consulte a notificação de <A href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?LinkId=268785</A>configuração na biblioteca do TechNet em.

    
    </div>

  - O pacote de gerenciamento de monitoramento ativo (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) testa proativamente os principais componentes do Lync Server, como entrar no sistema, trocar mensagens instantâneas ou fazer chamadas para um telefone localizado no Public comutado rede telefônica (PSTN). Esses testes são conduzidos usando os cmdlets de transação sintéticas do Lync Server. Por exemplo, você pode usar o cmdlet **Test-CsIM**para simular conversas por mensagens instantâneas entre usuários de teste. Se a simulação de conversa falhar, um alerta é gerado.

Você deve importar os pacotes de gerenciamento. Se você não importar os pacotes de gerenciamento, não poderá usar o Operations Manager para monitorar eventos do Lync Server ou executar transações sintéticas do Lync Server.

O pacote de gerenciamento de componente e usuário é usado apenas para monitorar o Lync Server 2013. Se você estiver em um cenário de coexistência, em que o Lync Server 2013 e o Lync Server 2010 estão instalados, você deverá continuar a usar os pacotes de gerenciamento do Lync Server 2010 para seus computadores com o Lync Server 2010.

<div>


> [!NOTE]  
> Os pacotes de gerenciamento do Lync Server 2010 incluem o pacote de gerenciamento de monitoramento do Lync Server 2010 e o pacote de gerenciamento de monitoramento de chat de grupo do Lync Server 2010.



</div>

Você pode usar uma destas ferramentas para importar pacotes de gerenciamento:

  - **System Center Operations Manager**   com este método, você usa o Operations Manager para adicionar o monitoramento para o Lync Server.

  - **Shell do Operations Manager**   você pode usar o Shell do Operations Manager para importar diretamente ou solucionar quaisquer problemas que encontrar ao importar pacotes de gerenciamento usando o console do System Center Operations Manager.

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Importando os pacotes de gerenciamento usando o System Center Operations Manager

1.  Baixe os arquivos Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp e Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.

2.  No System Center Operations Manager, clique em **Administração**.

3.  No painel **Administração**, clique com o botão direito do mouse em **Pacotes de gerenciamento** e, em seguida, clique em **Importar pacotes de gerenciamento**.

4.  Na caixa de diálogo **Selecinar pacotes de gerenciamento**, clique em **Adicionar** e, em seguida, em **Adicionar do disco**.

5.  Na caixa de diálogo **conexão do catálogo online** , clique em **Cancelar** para impedir que o Operations Manager fique online para ver se há alguma dependência para os pacotes de gerenciamento do Lync Server. Se você estiver usando o System Center Operations Manager 2012, clique em **não**.

6.  Na caixa de diálogo **Selecionar pacotes de gerenciamento para importar**, localize e selecione os arquivos **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** e **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp**. Em seguida, clique em **Abrir**. Para selecionar diversos arquivos na caixa de diálogo, mantenha a tecla Ctrl pressionada enquanto clica em outros arquivos.

7.  Na caixa de seleção **Selecionar pacotes de gerenciamento**, clique em **Instalar**. Se receber uma mensagem de erro e a instalação falhar, geralmente isso signfica que os arquivos dos pacotes de gerenciamento estão em uma pasta protegida pelo Controle de conta de usuário do Windows. Se isso ocorrer, copie os arquivos para outra pasta e reinicie o processo de intalação e importação.

8.  Na caixa de diálogo **Selecionar pacotes de gerenciamento**, clique em **Fechar**. A conclusão do processo de importação e instalação pode levar muitos minuto

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a>Importando pacotes de gerenciamento usando o Shell do Operations Manager

Em geral, é mais fácil importar os pacotes de gerenciamento usando o Operations Manager. no entanto, se ocorrer um erro e a importação falhar, o console nem sempre fornecerá os relatórios de erro adequados. Por comparação, o Shell do Operations Manager oferece informações detalhadas. Se você estiver usando o Operations Manager e tiver problemas para importar um pacote de gerenciamento, importe o pacote usando o Shell do Operations Manager. O Shell do Operations Manager fornece mais informações que podem ajudá-lo a determinar o motivo da falha da importação.

Se você estiver usando o System Center Operations Manager 2007 R2, conclua o procedimento a seguir:

1.  Clique em **Iniciar**, em **todos os programas**, em **System Center Operations Manager 2007 R2**e em **shell do Operations Manager**.

2.  No Shell do Operations Manager, digite o seguinte comando no prompt de comando, usando o caminho real para a sua cópia do arquivo Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp e pressione ENTER:
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  Depois de importar o primeiro pacote de gerenciamento, repita o processo usando o caminho do arquivo Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  Feche o Shell do Operations Manager.

Se você estiver usando o System Center Operations Manager 2012, conclua este procedimento:

1.  Clique **em Iniciar**, **em todos os programas**, em **Microsoft System Center 2012**, em **Operations Manager**e em **shell do Operations Manager**.

2.  No Shell do Operations Manager, digite o seguinte comando no prompt de comando, usando o caminho real para a sua cópia do arquivo Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp e pressione ENTER:
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  Depois de importar o primeiro pacote de gerenciamento, repita o processo usando o caminho até sua cópia do arquivo Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>

