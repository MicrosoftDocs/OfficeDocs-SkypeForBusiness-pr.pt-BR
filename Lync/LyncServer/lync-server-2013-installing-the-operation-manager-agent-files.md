---
title: 'Lync Server 2013: instalando os arquivos do agente do Operation Manager'
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
ms.openlocfilehash: 0f75e9b6f8c3f7eb7151cf0d67a62f5e2a03a65f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725951"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-operation-manager-agent-files-in-lync-server-2013"></a>Instalando os arquivos do agente do Operation Manager no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-20_

Para instalar os arquivos de agente do Operations Manager no computador, conclua as etapas a seguir.

1.  Na mídia de configuração do System Center, clique duas vezes em **SetupOM. exe**.

2.  Na configuração do System Center Operation Manager, clique em **instalar o agente do Operations Manager**.

3.  No assistente de configuração do System Center, na página **Bem-vindo ao assistente de configuração do System Center Operations Manager** , clique em **Avançar**.

4.  Na página **pasta de destino** , selecione a pasta onde os arquivos de agente do Operations Manager serão instalados e clique em **Avançar**.

5.  Na página **configuração do grupo de gerenciamento** , selecione **especificar informações do grupo de gerenciamento**e clique em **Avançar**.

6.  Na página **configuração do grupo de gerenciamento** , digite o nome do grupo de gerenciamento do Operations Manager na caixa **nome do grupo de gerenciamento** e digite o nome do host do servidor do Operations Manager (por exemplo, ATL-SCOM-001) na caixa servidor de **Gerenciamento** . Se você tiver alterado o número da porta usado pelo Operations Manager, digite o novo número de porta na caixa porta do servidor de gerenciamento. Caso contrário, deixe a porta com o valor padrão de 5723 e clique em **Avançar**.

7.  Na página da **conta de ação do agente** , selecione **sistema local**e, em seguida, clique em **Avançar**.

8.  Na página **Microsoft Update** , selecione **não desejo usar o Microsoft Update**e clique em **Avançar**.

9.  Na página **pronto para instalar** , clique em **instalar**.

10. Na página **concluindo o assistente de configuração do System Center Operations Manager** , clique em **concluir**.

11. Clique em **Sair**.

Se estiver usando o System Center 2007 R2, você pode verificar se o agente foi criado clicando em **Iniciar**, em **todos os programas**, em **System Center Operations Manager 2007 R2**e, em seguida, em **shell do Operations Manager**. In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:

    Get-Agent 

Uma lista de todos os seus agentes do Operations Manager será exibida na tela.

Se você estiver usando o System Center 2012, execute este comando no Shell operações do 2012 Manager:

    Get-SCOMAgent

</div>

<span> </span>

</div>

</div>

</div>

