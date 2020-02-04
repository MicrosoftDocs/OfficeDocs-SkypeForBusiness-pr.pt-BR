---
title: Re-ativar servidor após o Assistente de Configuração de Segurança fechar portas no IIS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Re-activate server after Security Configuration Wizard closes ports in IIS
ms:assetid: cb8e17cf-f8c1-4099-b63b-c242d656c26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398851(v=OCS.15)
ms:contentKeyID: 48185644
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f6642906c1855575fb8077846eef6646bfb37531
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746871"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a>Re-ativar servidor após o Assistente de Configuração de Segurança fechar portas no IIS

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-01_

Algumas funções do Lync Server 2013 executam serviços Web na porta do serviços de informações da Internet (IIS) 4443. Executar o assistente de implantação do Lync Server, bootstrapper. exe ou usar o cmdlet **Enable-CsComputer** cria uma exceção no firewall e abre a porta. Se você executar o assistente de configuração de segurança do Windows Server 2008 R2 (ou outros scripts de proteção), a porta 4443 será bloqueada e os clientes externos não poderão entrar em contato com os serviços Web. Para reabrir a porta, você pode modificar a exceção do firewall diretamente ou ativar novamente o servidor.

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a>Para reativar o servidor usando o assistente de implantação

1.  Na página do assistente de implantação do Lync Server, clique em **executar** ao lado da **etapa 2: configurar ou remover componentes do Lync Server**.

2.  Na página **configurar componentes do Lync Server** , clique em **Avançar**.

3.  Na página **comandos em execução** , quando o status da tarefa for exibido como concluído, clique em **concluir**.
    
    <div>
    

    > [!NOTE]
    > Você também pode usar bootstrapper. exe ou <STRONG>Enable-CsComputer</STRONG> para ativar novamente o servidor.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

