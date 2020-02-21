---
title: 'Lync Server 2013: instalar componentes de servidor do Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server server components
ms:assetid: 186aed6e-7adf-4a92-9f2e-f9a4de5ff202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398239(v=OCS.15)
ms:contentKeyID: 48183528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8f15afbb1602f369a063826c2196387dcff819b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-server-components-for-lync-server-2013"></a>Instalar componentes de servidor do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-05-05_

Antes de seguir estas etapas, verifique se você está conectado ao servidor com uma conta de usuário de domínio que seja um administrador local e um membro do grupo RTCUniversalReadOnlyAdmins no Active Directory.

O assistente de implantação do Lync Server é usado para instalar os componentes necessários para cada função do Lync Server e para ativar o servidor. Este artigo descreve as etapas de implantação de um servidor Standard Edition ou de um servidor front-end na sua infraestrutura do Lync.

<div>

## <a name="to-install-lync-server-components"></a>Instalação dos componentes do Lync Server

1.  Se o assistente de implantação do Lync Server não estiver em execução, inicie-o no servidor em que você deseja instalar o Lync.

2.  Clique em **instalar ou atualizar o sistema do Lync Server**.

3.  No assistente de implantação, confirme se a **etapa 1: instalar o repositório de configuração local** tem uma marca de seleção verde, o que significa que esse servidor tem uma cópia local do repositório instalado com êxito. Se ele não estiver selecionado, você precisará instalar o repositório de configuração local no servidor. Siga as etapas em [instalar o repositório de configuração local no Lync Server 2013](lync-server-2013-install-the-local-configuration-store.md) e volte aqui.

4.  Quando estiver pronto para instalar os componentes do Lync Server 2013 no servidor, clique em **executar** ao lado de **etapa 2: instalar ou remover componentes do Lync Server**.

5.  Na página **configurar componentes do Lync Server** , clique em **Avançar** para configurar componentes conforme definido na topologia publicada.

6.  A página **executando comandos** exibirá um resumo dos comandos e informações de instalação à medida que a configuração ocorrer. Quando terminar, você poderá usar a lista para selecionar um log a ser exibido e, em seguida, clique em **Exibir log**.

7.  Quando a instalação dos componentes do Lync Server 2013 é concluída e você analisou os logs conforme necessário, clique em **concluir** para concluir esta etapa na instalação.
    
    <div>
    

    > [!NOTE]  
    > Se você for solicitado a reiniciar o servidor (o que pode acontecer se a experiência da área de trabalho do Windows precisar ser instalada), definitivamente faça isso. Quando o computador fizer o backup e a execução, você precisará executar estas etapas novamente, começando pela etapa três listada acima (basicamente, execute a etapa 2 no assistente de implantação mais uma vez).

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

