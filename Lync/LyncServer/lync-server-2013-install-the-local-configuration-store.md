---
title: 'Lync Server 2013: Instalar o repositório de Configuração Local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install the Local Configuration store
ms:assetid: b563030d-d338-411f-9611-28d5eb4b3238
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412874(v=OCS.15)
ms:contentKeyID: 48185180
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 135dedc38bbc24dd69dfd44b74c70db8e3397252
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-local-configuration-store-in-lync-server-2013"></a>Instalar o repositório de Configuração Local no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-06-27_

Antes de seguir essas etapas, verifique se você está conectado ao servidor com uma conta de usuário de domínio que seja um administrador local e um membro do grupo RTCUniversalReadOnlyAdmin.

Para poder fazer algo com o assistente de implantação do Lync Server, precisamos que o repositório de configuração local exista em um servidor. O repositório de configuração local é uma cópia somente leitura do repositório de gerenciamento central, que é criado após a instalação local do SQL Server Express. O próprio repositório de gerenciamento central é adicionado ao banco de dados existente do SQL Server instalado no servidor Standard Edition ou no banco de dados baseado no SQL Server Express.

<div>


> [!IMPORTANT]  
> Se você não tiver executado a instalação do Lync Server 2013 nesse servidor antes, será solicitado que você solicite uma unidade e um caminho para instalar o Lync Server 2013. Isso permitirá que você instale em uma unidade diferente da unidade do sistema, se a sua organização exigir, ou se você tiver problemas de espaço. Você pode simplesmente alterar o caminho do local de instalação dos arquivos do Lync Server na caixa de diálogo Configurar para uma nova unidade disponível. Se você instalar os arquivos de instalação nesse caminho, incluindo o OCSCore. msi, o restante dos arquivos do Lync Server 2013 também será implantado.



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a>Para instalar o repositório de configuração local

1.  Na mídia de instalação, navegue até \\Setup\\AMD64\\setup. exe e clique em **OK**.

2.  Se você for solicitado a instalar o Microsoft Visual C++ 2012 Redistributable, clique em **Sim**.

3.  Na página **local de instalação do Lync Server 2013** , clique em **OK**.

4.  Na página **contrato de licença de usuário final** , examine os termos de licença, você precisará **aceitar os termos do contrato de licença**e, em seguida, clicar em **OK** para poder continuar.

5.  Na página Assistente de implantação, clique em **instalar ou atualizar o sistema do Lync Server**.

6.  Na página do **Lync Server 2013** , ao lado de **Step1: instalar o repositório de configuração local**, clique em **executar**.

7.  Na página **Instalar Configurações de Armazenamento Local**, verifique se a opção **Recuperar diretamente do repositório de Gerenciamento Central** está selecionada, e clique em **Próximo**.

8.  Quando a instalação de configuração do servidor local estiver concluída, clique em **concluir**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

