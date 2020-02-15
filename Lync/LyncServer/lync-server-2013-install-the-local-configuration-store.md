---
title: 'Lync Server 2013: instalar o repositório de configuração local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the Local Configuration store
ms:assetid: b563030d-d338-411f-9611-28d5eb4b3238
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412874(v=OCS.15)
ms:contentKeyID: 48185180
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00b4ffc463412064b578938516c4ea33b0dbb663
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029532"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-local-configuration-store-in-lync-server-2013"></a>Instalar o repositório de configuração local no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-06-27_

Antes de seguir estas etapas, verifique se você está conectado ao servidor com uma conta de usuário de domínio que seja um administrador local e um membro do grupo RTCUniversalReadOnlyAdmin.

Para poder fazer qualquer coisa com o assistente de implantação do Lync Server, precisamos que o repositório de configuração local exista em um servidor. O repositório de configuração local é uma cópia somente leitura do repositório de gerenciamento central, que é criado após a instalação local do SQL Server Express. O repositório de gerenciamento central em si é adicionado ao banco de dados do SQL Server existente instalado no servidor Standard Edition ou no banco de dados baseado no SQL Server Express.

<div>


> [!IMPORTANT]  
> Se você não tiver executado a instalação do Lync Server 2013 neste servidor antes, você será solicitado a fornecer uma unidade e um caminho para instalar o Lync Server 2013. Isso permitirá que você instale em uma unidade diferente da unidade do sistema, se sua organização exigir, ou se você tiver problemas de espaço. Você pode apenas alterar o caminho do local de instalação dos arquivos do Lync Server na caixa de diálogo Configurar para uma nova unidade disponível. Se você instalar os arquivos de instalação nesse caminho, incluindo o OCSCore. msi, o restante dos arquivos do Lync Server 2013 também será implantado.



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a>Para instalar o repositório Configuração Local

1.  Na mídia de instalação, navegue até \\instalar\\o\\AMD64. exe e clique em **OK**.

2.  Se você for solicitado a instalar o Microsoft Visual C++ 2012 Redistributable, clique em **Sim**.

3.  Na página **local de instalação do Lync Server 2013** , clique em **OK**.

4.  Na página **contrato de licença de usuário final** , revise os termos de licença, selecione **aceito os termos do contrato de licença**e clique em **OK** para continuar.

5.  Na página Assistente de Implantação, clique em **Instalar ou Atualizar o Sistema do Lync Server**.

6.  Na página **Lync Server 2013** , ao lado de **etapa 1: instalar repositório de configuração local**, clique em **executar**.

7.  Na página **instalar o repositório de configuração local** , verifique se a opção **recuperar diretamente do repositório de gerenciamento central** está selecionada e clique em **Avançar**.

8.  Quando a instalação da configuração do servidor local estiver concluída, clique em **concluir**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

