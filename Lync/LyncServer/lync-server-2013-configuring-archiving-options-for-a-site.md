---
title: 'Lync Server 2013: Configurando opções de arquivamento para um site'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Archiving options for a site
ms:assetid: 59b48fd9-d5fc-40b4-abae-e9cf89ee5573
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204930(v=OCS.15)
ms:contentKeyID: 48184247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14b0e29a2796c23c13a16bfb3e8a202a0a535aaa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-site-in-lync-server-2013"></a>Configurando opções de arquivamento para um site no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-09_

Você pode especificar opções de arquivamento a serem aplicadas a sites específicos criando e Configurando opções em uma configuração de arquivamento para cada um desses sites. Uma configuração de site substitui a configuração global, mas só se aplica ao site específico definido na configuração de site. Configurações de pool substituir configurações de site

Para obter detalhes sobre como funcionam as configurações de arquivamento, incluindo a hierarquia para configurações globais, de site e de pool, consulte [como o arquivamento funciona no Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou documentação de operações .

<div>


> [!NOTE]  
> Você deve especificar todas as opções adequadas nas configurações de arquivamento antes de habilitar o arquivamento.



</div>

<div>


> [!IMPORTANT]  
> Para habilitar o arquivamento, você deve especificar políticas de arquivamento para controlar o arquivamento de comunicações externas e internas ao nível global e, caso seja apropriado, nos níveis de site e usuário. Caso configure políticas de nível de usuário, você também deve atribuir as políticas de usuários para usuários específicos. Para obter detalhes sobre como criar e configurar as políticas de arquivamento, consulte <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Gerenciando o arquivamento de comunicações internas e externas no Lync Server 2013</A> na documentação de operações.



</div>

<div>

## <a name="to-configure-archiving-options-at-the-site-level"></a>Para configurar as opções de arquivamento no nível do site

1.  Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server 2013. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server 2013, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Configuração de Arquivamento**.

4.  Na página **Configuração do Arquivamento**, clique em **Nova** e depois em **Configuração do site**.

5.  Em **Selecionar um Site**, selecione o site a ser configurado para arquivamento.

6.  Em **Nova configuração de arquivamento**, na caixa de lista suspensa **Configuração de arquivamento**, execute uma das seguintes ações:
    
      - Para habilitar o arquivamento apenas para sessões de IM, clique em **Arquivar sessões de IM**.
    
      - Para habilitar o arquivamento para sessões de IM e conferências, clique em **Arquivar sessões de IM e webconferência**.
    
      - Para desabilitar o arquivamento da política, clique em **Desabilitar arquivamento**.

7.  Também em **Nova configuração de arquivamento**, execute uma das seguintes ações:
    
      - Para bloquear a atividade quando o arquivamento não estiver disponível, marque a caixa de seleção **Bloquear sessões de mensagem instantânea ou webconferência se o arquivamento falhar**.
    
      - Para usar o Microsoft Exchange Server para armazenar dados de arquivamento, clique na caixa de seleção **integração do Microsoft Exchange** .
    
      - Para habilitar a exclusão de dados, marque a caixa de seleção **Habilitar exclusão dos dados de arquivamento** e execute uma das seguintes ações:
        
          - Para especificar a exclusão após um número específico de dias, clique em **Excluir dados de arquivamento exportados e dados de arquivamento armazenados após uma duração máxima (dias)** e especifique o número de dias.
        
          - Para limitar a exclusão de dados de arquivamento que foram exportados, clique em **Excluir apenas dados de arquivamento exportados**.

8.  Clique em **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

