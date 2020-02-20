---
title: 'Lync Server 2013: instalar servidores de borda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Edge Servers
ms:assetid: 1655ab69-3899-4ee4-a1cc-8243bc1bfa0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398230(v=OCS.15)
ms:contentKeyID: 48183503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8060d72c6a5c727f0171d3082e7c17d0ed4ac5ab
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147204"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-edge-servers-for-lync-server-2013"></a>Instalar servidores de borda para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-08_

Você instala o Lync Server 2013 em servidores de borda usando o assistente de implantação do Lync Server. Executando o Assistente de Implantação em cada Servidor de Borda, é possível concluir a maioria das tarefas necessárias para configurar o Servidor de Borda. Para implantar o Lync Server 2013 em um servidor de borda, você já deve ter executado o construtor de topologias para definir e publicar sua topologia do servidor de borda e exportá-lo para a mídia que está disponível no servidor de borda. Para obter detalhes, consulte [cenários para acesso de usuário externo no Lync server 2013](lync-server-2013-scenarios-for-external-user-access.md) e [exporte sua topologia do Lync Server 2013 e copie-o para a mídia externa para instalação de borda](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).

Após usar o assistente de implantação para instalar cada servidor de borda, instalar e atribuir os certificados necessários e iniciar os serviços necessários, você poderá concluir a instalação usando as informações em [Configurando o suporte para acesso de usuário externo no Lync server 2013](lync-server-2013-configuring-support-for-external-user-access.md) para habilitar e configurar o acesso de usuário externo e as informações em [verificar sua implantação de borda no Lync 2013 Server](lync-server-2013-verifying-your-edge-deployment.md)

<div>

## <a name="to-install-an-edge-server"></a>Para instalar um Servidor de Borda

1.  Faça logon no computador no qual deseja instalar seu Servidor de Borda como um membro do grupo de Administradores locais ou como uma conta com direitos e permissões de usuário equivalentes.

2.  Verifique se o arquivo de configuração de topologia criado usando o construtor de topologias e, em seguida, exportado e copiado para a mídia externa, está disponível no servidor de borda (por exemplo, acesso à unidade USB na qual você copiou o arquivo de configuração de topologia ou verifique acesso ao compartilhamento de rede onde você copiou o arquivo).

3.  Iniciar o assistente de implantação.
    
    <div>
    

    > [!NOTE]  
    > Se você receber uma mensagem dizendo que você precisa instalar o Microsoft Visual C++ Redistribuível, clique em <STRONG>Sim</STRONG>. Na próxima caixa de diálogo, você pode aceitar o padrão <STRONG>Local de instalação</STRONG> ou clique em <STRONG>Pesquisar</STRONG> para selecionar um local e alterá-lo, depois clique em <STRONG>Instalar</STRONG>. Na próxima caixa de diálogo, marque a caixa de seleção <STRONG>Aceito os termos do contrato de licença</STRONG> e clique em <STRONG>OK</STRONG>.

    
    </div>

4.  No Assistente de Implantação, clique em **Instalar ou Atualizar o Sistema do Lync Server**.

5.  Depois que o assistente determinar o estado da implantação, em **Etapa 1. Instalar repositório de configuração local**, clique em **Executar** e, depois, faça o seguinte:
    
      - Na caixa de diálogo **Configurar réplica local do repositório de gerenciamento central**, clique em **Importar de um arquivo (Recomendado para os Servidores de Borda)**, vá para o local do arquivo de configuração da topologia, selecione o arquivo .zip, clique em **Abrir** e depois em **Avançar**.
    
      - O Assistente de Implantação lê as informações de configuração do arquivo de configuração e grava o arquivo de configuração XML no computador local.
    
      - Depois que o processo de **Execução de Comandos** for concluído, clique em **Concluir**.

6.  No assistente de implantação, clique em **etapa 2: instalar ou remover componentes do Lync Server** para instalar os componentes de borda do lync Server 2013 especificados no arquivo de configuração XML que está armazenado no computador local.

7.  Após concluir a instalação, use as informações em [set up Edge Certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md) para instalar e atribuir os certificados necessários antes de iniciar os serviços.

</div>

</div>

<span> </span>

</div>

</div>

</div>

