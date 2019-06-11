---
title: 'Lync Server 2013: importando os pacotes de gerenciamento do Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Importing the Lync Server 2013 management packs
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205052(v=OCS.15)
ms:contentKeyID: 48184690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70c753334ea9a046c6081a73ce70e4de00de9188
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829022"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="importing-the-lync-server-2013-management-packs"></a>Importando os pacotes de gerenciamento do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-22_

Você pode estender os recursos do System Center Operations Manager Instalando pacotes de gerenciamento — software que determina quais itens o System Center Operations Manager pode monitorar e como esses itens devem ser monitorados e como os alertas devem ser acionados e menciona. O Lync Server 2013 inclui dois pacotes de gerenciamento do System Center Operations Manager que fornecem os seguintes recursos:

  - O componente e o pacote de gerenciamento de usuários (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) controla problemas do Lync Server gravados em logs de eventos, registrados por contadores de desempenho, ou registrados nos registros de detalhes de chamadas (CDR) ou na qualidade da experiência (QoE) bancos. Para problemas críticos, o System Center Operations Manager pode ser configurado para notificar imediatamente os administradores por email, mensagem instantânea ou mensagens SMS (serviço de mensagens curtas). SMS é a tecnologia usada para enviar mensagens de texto de um dispositivo móvel para outro.)
    
    <div>
    

    > [!NOTE]  
    > Para obter detalhes sobre como configurar a notificação do Operations Manager, consulte a notificação Configurando na biblioteca do TechNet em <A href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?LinkId=268785</A>.

    
    </div>

  - O pacote de gerenciamento de monitoramento ativo (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) testa proativamente os principais componentes do Lync Server, como conectar-se ao sistema, trocar mensagens de chat ou fazer chamadas para um telefone localizado na pública comutada rede telefônica (PSTN). Esses testes são conduzidos usando cmdlets de transação sintéticas do Lync Server. Por exemplo, você pode usar o cmdlet **Test-CsIM** para simular uma conversa de mensagens instantâneas entre um par de usuários de teste. Se essa conversa de mensagens simulada falhar, um alerta será gerado.

Você precisa importar os pacotes de gerenciamento. Se você não importar os pacotes de gerenciamento, não poderá usar o Operations Manager para monitorar eventos do Lync Server ou executar transações sintéticas do Lync Server.

O pacote de gerenciamento de componentes e usuários só é usado para monitorar o Lync Server 2013. Se você estiver em um cenário de coexistência, no qual você tem o Lync Server 2013 e o Lync Server 2010 instalados, você deve continuar a usar os pacotes de gerenciamento do Lync Server 2010 para seus computadores com o Lync Server 2010.

<div>


> [!NOTE]  
> Os pacotes de gerenciamento do Lync Server 2010 incluem o pacote de gerenciamento de monitoramento do Lync Server 2010 e o pacote de gerenciamento de monitoramento de chat de grupo do Lync Server 2010.



</div>

Você pode usar uma destas ferramentas para importar pacotes de gerenciamento:

  - **System Center Operations Manager**   com esse método, use o Gerenciador de operações para adicionar o monitoramento do Lync Server.

  - **Shell do Operations Manager**   você pode usar o Shell do Operations Manager para importar diretamente ou solucionar problemas encontrados ao importar pacotes de gerenciamento usando o console do System Center Operations Manager.

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Importando os pacotes de gerenciamento usando o System Center Operations Manager

1.  Baixe os arquivos Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp e Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.

2.  No System Center Operations Manager, clique em **Administração**.

3.  No painel **Administração** , clique com o botão direito do mouse em **pacotes de gerenciamento**e, em seguida, clique em **importar pacotes de gerenciamento**.

4.  Na caixa de diálogo **Selecionar Pacotes de Gerenciamento**, clique em **Adicionar** e, em seguida, em **Adicionar do disco**.

5.  Na caixa de diálogo **conexão de catálogo online** , clique em **Cancelar** para impedir que o Operations Manager fique online para ver se há dependências para os pacotes de gerenciamento do Lync Server. Se você estiver usando o System Center Operations Manager 2012, clique em **não**.

6.  Na caixa de diálogo **selecionar pacotes de gerenciamento a serem** importados, localize e selecione os arquivos **Microsoft.ls.2013.Monitoring.ActiveMonitoring.MP** e **Microsoft.ls.2013.Monitoring.ComponentAndUser.MP** e, em seguida, clique em **abrir**. Para selecionar vários arquivos na caixa de diálogo, clique no primeiro arquivo, mantenha pressionada a tecla CTRL e clique no segundo arquivo.

7.  Na caixa de seleção **Selecionar pacotes de gerenciamento**, clique em **Instalar**. Se receber uma mensagem de erro e a instalação falhar, geralmente isso significa que os arquivos dos pacotes de gerenciamento estão em uma pasta protegida pelo Controle de conta de usuário do Windows. Se isso ocorrer, copie os arquivos para uma pasta diferente e reinicie o processo de importação e instalação.

8.  Na caixa de diálogo **Selecionar pacotes de gerenciamento**, clique em **Fechar**. Observe que o processo de importação e instalação pode exigir vários minutos para ser concluído.

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a>Importando pacotes de gerenciamento usando o Shell do Operations Manager

Em geral, é mais fácil importar os pacotes de gerenciamento usando o Gerenciador de operações. no entanto, se ocorrer um erro e a importação falhar, o console nem sempre fornecerá os relatórios de erro adequados. Por comparação, o Shell do Operations Manager fornece informações detalhadas. Se você estiver usando o Operations Manager e tiver problemas para importar um pacote de gerenciamento, importe o pacote usando o Shell do Operations Manager. O Shell do Operations Manager fornece mais informações que podem ajudá-lo a determinar por que houve falha na importação.

Se você estiver usando o System Center Operations Manager 2007 R2, conclua o seguinte procedimento:

1.  Clique em **Iniciar**, em **todos os programas**, em **System Center Operations Manager 2007 R2**e, em seguida, clique em **shell do Operations Manager**.

2.  No Shell do Operations Manager, digite o seguinte comando no prompt de comando, usando o caminho real para a sua cópia do arquivo Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp e, em seguida, pressione ENTER:
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  Depois de importar o primeiro pacote de gerenciamento, repita o processo usando o caminho para a sua cópia do arquivo Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  Feche o Shell do Operations Manager.

Se você estiver usando o System Center Operations Manager 2012, conclua este procedimento em vez disso:

1.  Clique em **Iniciar**, **Todos os Programas**, **Microsoft System Center 2012**, **Operations Manager** e **Shell do Operations Manager**.

2.  No Shell do Operations Manager, digite o seguinte comando no prompt de comando, usando o caminho real para a sua cópia do arquivo Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp e, em seguida, pressione ENTER:
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  Depois de importar o primeiro pacote de gerenciamento, repita o processo usando o caminho para a sua cópia do arquivo Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>

