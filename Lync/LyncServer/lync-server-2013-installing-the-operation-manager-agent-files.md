---
title: 'Lync Server 2013: instalando os arquivos do agente do Gerenciador de operações'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Operation Manager agent files
ms:assetid: e2246c44-0c75-43fc-8b04-26e53c5dd572
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205345(v=OCS.15)
ms:contentKeyID: 48185692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0216c05dd039f907d0ac54ff8afa13f6015a923d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534798"
---
# <a name="installing-the-operation-manager-agent-files-in-lync-server-2013"></a>Instalando os arquivos do agente do Operation Manager no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-20_

Para instalar os arquivos do agente do Operations Manager no computador, conclua as etapas a seguir.

1.  Na mídia de instalação do System Center, clique duas vezes em **SetupOM.exe**.

2.  Na instalação do System Center Operation Manager, clique em **instalar o agente do Operations Manager**.

3.  No assistente de instalação do System Center, na página **Bem-vindo ao assistente de instalação do System Center Operations Manager** , clique em **Avançar**.

4.  Na página **pasta de destino** , selecione a pasta onde os arquivos do agente do Operations Manager serão instalados e clique em **Avançar**.

5.  Na página **configuração do grupo de gerenciamento** , selecione **especificar informações do grupo de gerenciamento**e clique em **Avançar**.

6.  Na página **configuração do grupo de gerenciamento** , digite o nome do grupo de gerenciamento do Operations Manager na caixa **nome do grupo de gerenciamento** e, em seguida, digite o nome do host do seu servidor do Operations Manager (por exemplo, ATL-SCOM-001) na caixa servidor de **Gerenciamento** . Se você tiver alterado o número da porta usada pelo Operations Manager, digite o novo número de porta na caixa porta do servidor de gerenciamento. Caso contrário, deixe a porta no valor padrão de 5723 e clique em **Avançar**.

7.  Na página **conta de ação do agente** , selecione **sistema local**e clique em **Avançar**.

8.  Na página **Microsoft Update** , selecione **eu não desejo usar o Microsoft Update**e clique em **Avançar**.

9.  Na página **pronto para instalar** , clique em **instalar**.

10. Na página **concluindo o assistente de instalação do System Center Operations Manager** , clique em **concluir**.

11. Clique em **Sair**.

Se você estiver usando o System Center 2007 R2, é possível verificar se o agente foi criado clicando em **Iniciar**, em **todos os programas**, em **System Center Operations Manager 2007 R2**e, em seguida, em **shell do Operations Manager**. No Shell do Operations Manager, digite o seguinte comando do Windows PowerShell e pressione ENTER:

    Get-Agent 

Uma lista de todos os seus agentes do Operations Manager será exibida na tela.

Se você estiver usando o System Center 2012, execute este comando no Shell do Gerenciador de operações 2012:

    Get-SCOMAgent

</div>

<span> </span>

</div>

</div>

</div>

