---
title: 'Lync Server 2013: Instalar Servidores de Borda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install Edge Servers
ms:assetid: 1655ab69-3899-4ee4-a1cc-8243bc1bfa0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398230(v=OCS.15)
ms:contentKeyID: 48183503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 211baa13f80e89fa081b6bf65d4bd7e90d50d000
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-edge-servers-for-lync-server-2013"></a>Instalar Servidores de Borda para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-08_

Você instala o Lync Server 2013 em servidores de borda usando o assistente de implantação do Lync Server. Ao executar o assistente de implantação em cada servidor de borda, você pode concluir a maioria das tarefas necessárias para configurar o servidor de borda. Para implantar o Lync Server 2013 em um servidor de borda, você já deve ter executado o construtor de topologias para definir e publicar a topologia do servidor de borda e exportá-la para a mídia que está disponível no servidor de borda. Para obter detalhes, consulte [cenários para acesso de usuários externos no Lync server 2013](lync-server-2013-scenarios-for-external-user-access.md) e [exporte sua topologia do Lync Server 2013 e copie-o para mídia externa para instalação do Edge](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).

Depois de usar o assistente de implantação para instalar cada servidor de borda, instalar e atribuir os certificados obrigatórios e iniciar os serviços necessários, você pode concluir a configuração usando as informações em Configurando o [suporte para acesso de usuários externos no Lync Server 2013 ](lync-server-2013-configuring-support-for-external-user-access.md)para habilitar e configurar o acesso de usuários externos e as informações para [verificar a implantação de borda no Lync Server 2013](lync-server-2013-verifying-your-edge-deployment.md) para validar a configuração, incluindo a conectividade do servidor e do cliente.

<div>

## <a name="to-install-an-edge-server"></a>Para instalar um servidor de borda

1.  Faça logon no computador no qual você deseja instalar o servidor de borda como membro do grupo Administradores local ou de uma conta com direitos e permissões de usuário equivalentes.

2.  Verifique se o arquivo de configuração de topologia que você criou usando o construtor de topologias e depois exportado e copiado para mídia externa está disponível no servidor de borda (por exemplo, acesso à unidade USB na qual você copiou o arquivo de configuração de topologia ou verifique acesso ao compartilhamento de rede onde você copiou o arquivo).

3.  Iniciar o assistente de implantação.
    
    <div>
    

    > [!NOTE]  
    > Se você receber uma mensagem dizendo que precisa instalar o Microsoft Visual C++ Redistributable, clique em <STRONG>Sim</STRONG>. Na próxima caixa de diálogo, você pode aceitar o <STRONG>local de instalação</STRONG> padrão ou clicar em <STRONG>procurar</STRONG> para selecionar um local alternativo e, em seguida, clicar em <STRONG>instalar</STRONG>. Na caixa de diálogo seguinte, marque a caixa de seleção aceito <STRONG>os termos do contrato de licença</STRONG> e clique em <STRONG>OK</STRONG>.

    
    </div>

4.  No assistente de implantação, clique em **instalar ou atualizar o sistema do Lync Server**.

5.  Após o assistente determinar o estado de implantação, para a **etapa 1. Instale o repositório de configuração local**, clique em **executar** e siga este procedimento:
    
      - Na caixa de diálogo **Configurar réplica local do repositório de gerenciamento central** , clique em **importar de um arquivo (recomendado para servidores de borda)**, vá para o local do arquivo de configuração de topologia exportado, selecione o arquivo. zip, clique em **abrir**e, em seguida, clique em **Avançar**.
    
      - O assistente de implantação lê as informações de configuração do arquivo de configuração e grava o arquivo de configuração XML no computador local.
    
      - Depois que o processo de **Execução de Comandos** for concluído, clique em **Concluir**.

6.  No assistente de implantação, clique em **etapa 2: configurar ou remover componentes do Lync Server** para instalar os componentes de borda do lync Server 2013 especificados no arquivo de configuração XML armazenado no computador local.

7.  Depois de concluir a instalação, use as informações em [configurar certificados de borda do Lync Server 2013](lync-server-2013-set-up-edge-certificates.md) para instalar e atribuir os certificados obrigatórios antes de iniciar serviços.

</div>

</div>

<span> </span>

</div>

</div>

</div>

