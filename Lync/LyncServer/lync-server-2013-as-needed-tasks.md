---
title: 'Lync Server 2013: tarefas necessárias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: As-needed tasks
ms:assetid: b66bc6fe-f138-4cf4-ba7f-aee9a3e0497e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722431(v=OCS.15)
ms:contentKeyID: 63969643
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 344512a1dd4db44b8290efdcc726275b4a6898de
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738401"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="as-needed-tasks-in-lync-server-2013"></a>Tarefas o mais necessárias no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-08-18_

Execute as seguintes tarefas, conforme necessário. Eles também são cobertos pelos procedimentos padrão com frequência:

  - **Auditoria de segurança completa   ** Você pode realizar essa auditoria regularmente, em resposta a uma atualização ou reformulação do sistema de mensagens ou em resposta a uma falha de segurança tentada (ou bem-sucedida). O procedimento pode envolver verificações de porta em servidores e firewalls, auditorias de correções de segurança e testes de penetração de terceiros.

  - **Substituir certificados prestes a**   verificar se a validade dos certificados do Lync Server é uma das tarefas semanais regulares e, como parte do procedimento, um administrador deve ter um registro de todas as datas de vencimento dos certificados. Este registro permite que um administrador crie uma notificação quando um certificado específico estiver prestes a expirar e ser substituído conforme necessário.

  - **Atualizando linhas de base de desempenho**   atualize as linhas de base de desempenho após uma atualização ou alteração de configuração. Sua organização pode usar linhas de base para medir alterações de desempenho e detectar problemas que afetam o desempenho do sistema.

  - **O gerenciamento**   da configuração inicial do pool de Enterprise de pools corporativos, servidores Standard Edition e quaisquer outros servidores no ambiente da organização foram feitos durante a implantação dos servidores individuais. O gerenciamento pós-implantação de servidores e pools para servidores Standard Edition e pools corporativos inclui as seguintes tarefas:
    
      - Gerenciamento de servidores front-end
    
      - Como gerenciar a conferência via Web
    
      - Como gerenciar a conferência
    
      - Alterar as credenciais da conta de serviço
    
      - Como gerenciar bancos de dados
    
      - Iniciando e parando serviços e desativando funções de servidor
    
      - Removendo servidores e funções de servidor, removendo pools e descomissionando servidores e pools

  - **Gerenciando o uso**   você pode configurar o Lync Server 2013 para fornecer os recursos e funcionalidades mais apropriados para a sua organização. Isso inclui o seguinte:
    
      - Gerenciando o suporte para reuniões do Web conferência locais
    
      - Gerenciar o uso de grupos de distribuição para enviar mensagens instantâneas
    
      - Gerenciando contatos, presença e consultas
    
      - Configurando a filtragem de versão do cliente
    
      - Configurando a filtragem inteligente de IM
    
      - Configurando o arquivamento, a gravação de detalhes da chamada e a conformidade da reunião

  - **Gerenciamento de conectividade**   do servidor de borda o gerenciamento contínuo dos servidores e das configurações necessárias para fornecer conectividade externa inclui o seguinte:
    
      - Gerenciando a conectividade entre servidores internos e servidores de borda
    
      - Configurando interfaces internas e externas e certificados para servidores Edge
    
      - Gerenciando o acesso de parceiro federado

  - **Administrar o catálogo**   de endereços a administração de servidores de catálogo de endereços inclui o seguinte:
    
      - Configurando a normalização do telefone do servidor catálogo de endereços
    
      - Gerenciando o servidor de catálogo de endereços na linha de comando

  - **Gerenciar contas**   de usuário gerenciamento de contas de usuário inclui o seguinte:
    
      - Habilitando contas de usuário para o Lync Server
    
      - Configurar usuários do Lync Server usando o assistente
    
      - Configurar propriedades individuais da conta de usuário do Lync Server
    
      - Procurando usuários do Lync Server
    
      - Movendo usuários do Lync Server
    
      - Excluindo usuários do Lync Server

  - **Analisando os arquivos**   de log do Lync Server 2013 uma ferramenta muito útil, geralmente usada para solução de problemas, é a ferramenta de log do Lync Server 2013 descrita em detalhes sobre como [usar a ferramenta de log do Lync Server 2013](http://technet.microsoft.com/en-us/library/gg558599.aspx).

Como a ferramenta de log gera arquivos de log (em uma base por servidor), esses arquivos de log podem ser visualizados e analisados usando-se a ferramenta de rastreamento, se as ferramentas do Microsoft Office Server 12 Resource Kit estiverem instaladas no computador. Caso contrário, os logs também podem ser analisados usando um editor de texto, que é muito menos transparente e mais complexo do que usar o utilitário de rastreamento.

Para exibir e analisar mensagens de protocolo

Na ferramenta de log, quando você tiver encerrado a sessão de depuração, clique em analisar arquivos de log para ver os arquivos de log usando a ferramenta de rastreamento. Você pode analisar logs de protocolo para os seguintes componentes:

  - Lync Server SipStack (SIP)

  - A S4 (SIP) do Lync Server

  - Tráfego de sinalização do Lync Server Conferencing (C3P), incluindo a MCU-C3P e o foco C3P

  - Tráfego da webconferência do Lync Server (PSOM)

  - Cliente da plataforma de cliente de comunicação unificada do Lync Server (UCCP)

  - Relatórios de erros do banco de dados de arquivamento

Para ajudar a organizar o desempenho das tarefas necessárias, consulte lista de verificação de operações necessárias.

<div>


> [!IMPORTANT]  
> Para obter procedimentos detalhados de administração e gerenciamento, consulte o guia de administração do Microsoft Lync Server 2013.



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a>Políticas de backup (e restauração) ou configurações de configuração

O Lync Server 2013 permite que você faça backup e restaure todo o sistema. IIf que você deseja fazer backup (e, em seguida, talvez um dia restaurar) uma única política ou um único conjunto de configurações, recuperar a política apropriada e, em seguida, canalizar esse objeto para o cmdlet Export-Clixml, que salva as informações da política como um arquivo XML:

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

Agora você pode experimentar o RedmondClientPolicy e alterar muitas das configurações. Se, em vez disso, você decidir restaurar a política antiga, digite:

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

Observe que essa abordagem funciona para a maioria das políticas e configurações, mas não funciona com alguns dos itens mais complexos, itens que contêm vários subobjetos (como as configurações de roteamento, que contêm muitas rotas de voz separadas).

</div>

</div>

<span> </span>

</div>

</div>

</div>

