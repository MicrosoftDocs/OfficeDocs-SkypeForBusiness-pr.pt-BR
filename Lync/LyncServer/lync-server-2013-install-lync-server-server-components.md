---
title: 'Lync Server 2013: Instalar componentes de servidor do Lync Server'
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
ms.openlocfilehash: 4f039f9363469663410f08f078a3b7e17a170075
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763715"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-server-components-for-lync-server-2013"></a>Instalar componentes de servidor para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-05-05_

Antes de seguir essas etapas, verifique se você está conectado ao servidor com uma conta de usuário de domínio que seja um administrador local e um membro do grupo RTCUniversalReadOnlyAdmins no Active Directory.

O assistente de implantação do Lync Server é usado para instalar os componentes necessários para cada função do Lync Server e ativar o servidor. Este artigo orienta você pelas etapas de implantação de um servidor Standard Edition ou de um servidor front-end na sua infraestrutura do Lync.

<div>

## <a name="to-install-lync-server-components"></a>Para instalar os componentes do Lync Server

1.  Se o assistente de implantação do Lync Server não estiver em execução, inicie-o no servidor em que você deseja instalar o Lync.

2.  Clique em **instalar ou atualizar o sistema do Lync Server**.

3.  No assistente de implantação, confirme se a **etapa 1: instalar o repositório de configuração local** tem uma marca de seleção verde, o que significa que o servidor tem uma cópia local da loja instalada com êxito. Se não estiver marcada, você precisará instalar o repositório de configuração local no servidor. Siga as etapas em [instalar o repositório de configuração local no Lync Server 2013](lync-server-2013-install-the-local-configuration-store.md) e, em seguida, volte aqui.

4.  Quando estiver pronto para instalar os componentes do Lync Server 2013 em seu servidor, clique em **executar** ao lado da **etapa 2: configurar ou remover componentes do Lync Server**.

5.  Na página **configurar componentes do Lync Server** , clique em **Avançar** para configurar componentes conforme definido na sua topologia publicada.

6.  A página **comandos em execução** exibirá um resumo dos comandos e informações de instalação à medida que a configuração ocorre. Quando terminar, use a lista para selecionar um log para exibição e clique em **Exibir Log**.

7.  Quando a instalação dos componentes do Lync Server 2013 for concluída e você tiver revisado os logs conforme necessário, clique em **concluir** para concluir esta etapa na instalação.
    
    <div>
    

    > [!NOTE]  
    > Se você for solicitado a reiniciar o servidor (o que pode acontecer se a experiência da área de trabalho do Windows precisar ser instalada), definitivamente faça isso. Quando o computador estiver em operação de backup e em execução, você precisará executar essas etapas novamente, começando da etapa três listadas acima (basicamente, execute a etapa 2 no assistente de implantação mais uma vez).

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

