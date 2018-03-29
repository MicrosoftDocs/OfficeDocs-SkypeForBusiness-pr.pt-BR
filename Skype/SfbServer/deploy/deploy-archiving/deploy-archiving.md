---
title: Implantar arquivamento no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50fa535c-7347-4e33-80a3-296748ef6666
description: 'Resumo: Leia este tópico para saber como implantar o arquivamento para Skype para Business Server 2015.'
ms.openlocfilehash: d218c59038b599f016f99cbce453f0bf1830a6f8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-archiving-for-skype-for-business-server-2015"></a>Implantar arquivamento no Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber como implantar o arquivamento para Skype para Business Server 2015.
  
Arquivamento é instalado automaticamente em cada servidor Front-End no seu Skype para implantação Business Server 2015, mas ainda é necessário executar a configuração inicial e etapas de configuração, antes de você pode usá-lo. Antes de começar, certifique-se de que você está familiarizado com os conceitos apresentados no [planejamento para arquivamento no Skype para Business Server 2015](../../plan-your-deployment/archiving/archiving.md).
  
## <a name="deployment-checklist"></a>Lista de verificação da implantação

O modo de configuração do arquivamento depende da opção de armazenamento escolhida: 
  
- Se você usar a integração do Microsoft Exchange para todos os usuários em sua implantação, você não precisará configurar Skype para políticas de arquivamento Business Server para seus usuários. Em vez disso, você pode configurar políticas de retenção de In-loco do Exchange para suportar o arquivamento para usuários hospedados no Exchange, com suas caixas de correio colocadas em retenção In-loco. Para obter detalhes sobre como configurar essas políticas, consulte a documentação de produto do Exchange.
    
- Se você não usar a integração do Microsoft Exchange para todos os usuários em sua implantação, você precisa adicionar Skype para Business Server arquivamento de bancos de dados (bancos de dados do SQL Server) para sua topologia, publicar a topologia atualizada e, em seguida, configurar políticas de arquivamento e configurações para seus usuários. Você pode implantar o arquivamento de bancos de dados ao mesmo tempo que você implante a topologia inicial ou depois que você tem implantado pelo menos um pool de Front-End ou servidor Standard Edition. Este documento descreve como implantar o arquivamento de bancos de dados adicionando-os a uma implantação existente.
    
Se você habilitar o arquivamento em um pool de Front-Ends ou em um Servidor Standard Edition, você deve habilitá-lo em todos os pools e servidores do mesmo tipo na sua implantação. Isso porque os usuários cujas comunicações precisam ser arquivadas podem ser convidados para grupos de conversa via IM ou reuniões hospedadas em um pool diferente. Se o arquivamento não estiver habilitado no pool no qual a conversa ou a reunião está hospedada, a sessão completa não poderá ser arquivada. Nesses casos, as IMs com usuários habilitados para arquivamento ainda poderão ser arquivadas, mas não arquivos de conteúdo de conferência e eventos de ingresso ou saída de conferências.
  
> [!IMPORTANT]
> Se o arquivamento for crucial na sua organização por motivos de conformidade, certifique-se implantar o arquivamento, configurar políticas e outras opções no nível apropriado e, em seguida, Ativar arquivamento para todos os usuários apropriados, antes de habilitar esses usuários para Skype para Servidor de negócios. 
  
A tabela a seguir fornece uma visão geral das etapas necessárias para implantar o arquivamento em uma topologia existente.
  
|**Fase**|**Etapas**|**Funções e associações de grupo**|**Documentação**|
|:-----|:-----|:-----|:-----|
|**Instalar pré-requisitos de hardware e software** <br/> |Para usar a integração do Microsoft Exchange (usando o Exchange para armazenamento de arquivamento para alguns ou todos os usuários), você precisa de uma implantação existente do Exchange.  <br/> Para usar bancos de dados de arquivamento separados (usando bancos de dados do SQL Server) para armazenamento de arquivamento para alguns ou todos os usuários, SQL Server no servidor que armazenará os dados de arquivamento.  <br/> O Arquivamento é executado nos Servidores Front-End de um pool Enterprise e Servidores Standard Edition. Não há requisitos adicionais de hardware ou software além daqueles necessários para instalar esses servidores.  <br/> |Usuário do domínio que é membro do grupo local de administradores.  <br/> |[Requisitos de servidor do Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Requisitos de ambiente para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [Requisitos de hardware e software para arquivamento no Skype para Business Server 2015](../../plan-your-deployment/archiving/hardware-and-software-requirements.md) <br/> [Planejar a integração do Skype para Exchange e de negócios](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) <br/> |
|**Criar a topologia interna apropriada para dar suporte ao arquivamento (somente se não usando a integração do Microsoft Exchange para todos os usuários em sua implantação)** <br/> |Execute o construtor de topologias para adicionar o Skype para arquivamento de bancos de dados (bancos de dados do SQL Server) do servidor de negócios à topologia e, em seguida, publique a topologia.  <br/> |Para definir a topologia a fim de incorporar bancos de dados de arquivamento, uma conta que é membro do grupo local de usuários.  <br/> Para publicar a topologia, uma conta que seja membro do grupo de administradores de domínio e do grupo RTCUniversalServerAdmins e que tem permissões de controle total (leitura/gravação/modificar) no compartilhamento de arquivos a serem usados para o Skype para repositório de arquivos do servidor de negócios (para que topologia Construtor pode configurar as DACLs necessárias).  <br/> |[Adicionar bancos de dados de arquivamento a uma implantação existente no Skype para Business Server 2015](add-archiving-databases.md) <br/> |
|**Configurar a autenticação de servidor-para-servidor (somente se estiver usando a integração do Microsoft Exchange)** <br/> |Configure servidores para habilitar a autenticação entre Skype para Business Server e o Exchange. É recomendável executar **Test-CsExchangeStorageConnectivity testuser_sipUri-pasta Dumpster** para validar a conectividade com o armazenamento de arquivamento antes de habilitar o arquivamento do Exchange. <br/> |Uma conta com permissões adequadas para gerenciar certificados nos servidores.  <br/> |Gerencie autenticação servidor para servidor  <br/> |
|**Configure políticas e opções de arquivamento** <br/> |Configurar o arquivamento, incluindo se devemos usar a integração do Microsoft Exchange, a política global e quaisquer políticas de site e de usuário (quando não usando a integração do Microsoft Exchange para todo o armazenamento de dados) e arquivamento específico opções, como o modo crítico e dados Exportar e limpeza.  <br/> Se estiver usando a integração com o Microsoft Exchange, configure as políticas de retenção de In-loco do Exchange conforme apropriado.  <br/> |Grupo RTCUniversalServerAdmins (somente Windows PowerShell) ou atribua usuários à função CSArchivingAdministrator ou CSAdministrator.  <br/> |[Configurar opções de arquivamento do Skype for Business Server 2015](configure-archiving-options.md) <br/> Documentação do produto do Exchange (se estiver usando a integração do Microsoft Exchange).  <br/> |
   

