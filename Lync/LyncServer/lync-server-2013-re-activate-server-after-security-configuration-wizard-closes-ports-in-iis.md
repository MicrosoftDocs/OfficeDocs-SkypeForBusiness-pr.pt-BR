---
title: Reativar servidor após o assistente de configuração de segurança fechar portas no IIS
description: Reativar servidor após o assistente de configuração de segurança fechar portas no IIS.
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
ms.openlocfilehash: d824845a7f89c28087a7b5d180a6ed017cb47ade
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579047"
---
# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a>Reativar servidor após o assistente de configuração de segurança fechar portas no IIS

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-01_

Algumas funções do Lync Server 2013 executam serviços Web na porta de serviços de informações da Internet (IIS) 4443. Executar o assistente de implantação do Lync Server, Bootstrapper.exe ou usar o cmdlet **Enable-CsComputer** cria uma exceção no firewall e abre a porta. Se você executar o assistente de configuração de segurança do Windows Server 2008 R2 (ou outros scripts de proteção), a porta 4443 será bloqueada, e os clientes externos não poderão entrar em contato com os serviços Web. Para reabrir a porta, você pode modificar a exceção do firewall diretamente ou reativar o servidor.

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a>Para reativar o servidor usando o Assistente de Implantação

1.  Na página Assistente de implantação do Lync Server, clique em **executar** ao lado de **etapa 2: instalar ou remover componentes do Lync Server**.

2.  Na página **Instalar componentes do Lync Server**, clique em **Avançar**.

3.  Na página **Executando Comandos**, quando o status da tarefa é exibido como concluído, clique em **Concluir**.
    
    <div>
    

    > [!NOTE]
    > Também é possível usar bootstrapper.exe ou <STRONG>Enable-CsComputer</STRONG> para reativar o servidor.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

