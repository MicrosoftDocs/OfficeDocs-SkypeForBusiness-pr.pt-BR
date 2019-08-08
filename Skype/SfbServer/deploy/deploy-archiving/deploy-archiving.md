---
title: Implantar o arquivamento para o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50fa535c-7347-4e33-80a3-296748ef6666
description: 'Resumo: Leia este tópico para saber como implantar o arquivamento do Skype for Business Server.'
ms.openlocfilehash: 8611f83b6e3504d860cf37a7ad2c24c20b446671
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234511"
---
# <a name="deploy-archiving-for-skype-for-business-server"></a>Implantar o arquivamento para o Skype for Business Server
 
**Resumo:** Leia este tópico para saber como implantar o arquivamento para o Skype for Business Server.
  
O arquivamento é instalado automaticamente em cada servidor front-end na implantação do Skype for Business Server, mas você ainda precisa executar as etapas de configuração e configuração iniciais para poder usá-lo. Antes de começar, certifique-se de estar familiarizado com os conceitos do [plano de arquivamento no Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).
  
## <a name="deployment-checklist"></a>Lista de verificação da implantação

O modo de configuração do arquivamento depende da opção de armazenamento escolhida: 
  
- Se você usa a integração do Microsoft Exchange para todos os usuários em sua implantação, não precisa configurar as políticas de arquivamento do Skype for Business Server para seus usuários. Em vez disso, configure as políticas de bloqueio do Exchange in loco para dar suporte ao arquivamento para usuários hospedados no Exchange, com as caixas de correio colocadas no bloqueio in-loco. Para obter detalhes sobre como configurar essas políticas, consulte a documentação do produto Exchange.
    
- Se você não usar a integração do Microsoft Exchange para todos os usuários em sua implantação, será necessário adicionar bancos de dados de arquivamento do Skype for Business Server (bancos de dados do SQL Server) à sua topologia, publicar a topologia atualizada e, em seguida, configurar as políticas de arquivamento e configurações para seus usuários. Você pode implantar bancos de dados de arquivamento ao mesmo tempo em que implanta sua topologia inicial ou depois de implantar pelo menos um pool de front-end ou um servidor Standard Edition. Este documento descreve como implantar bancos de dados de arquivamento adicionando-os a uma implantação existente.
    
Se você habilitar o arquivamento em um pool de Front-Ends ou em um Servidor Standard Edition, você deve habilitá-lo em todos os pools e servidores do mesmo tipo na sua implantação. Isso porque os usuários cujas comunicações precisam ser arquivadas podem ser convidados para grupos de conversa via IM ou reuniões hospedadas em um pool diferente. Se o arquivamento não estiver habilitado no pool no qual a conversa ou a reunião está hospedada, a sessão completa não poderá ser arquivada. Nesses casos, as IMs com usuários habilitados para arquivamento ainda poderão ser arquivadas, mas não arquivos de conteúdo de conferência e eventos de ingresso ou saída de conferências.
  
> [!IMPORTANT]
> Se o arquivamento for fundamental para a sua organização por motivos de conformidade, certifique-se de implantar o arquivamento, configurar políticas e outras opções no nível apropriado e ativar o arquivamento para todos os usuários apropriados antes de habilitar esses usuários para o Skype for Business Server. 
  
A tabela a seguir fornece uma visão geral das etapas necessárias para implantar o arquivamento em uma topologia existente.
  
|**Fase**|**Etapas**|**Funções e associações de grupo**|**Documentação**|
|:-----|:-----|:-----|:-----|
|**Instalar pré-requisitos de hardware e software** <br/> |Para usar a integração do Microsoft Exchange (usando o Exchange para arquivar o armazenamento para alguns ou todos os usuários), você precisa de uma implantação do Exchange existente.  <br/> Para usar bancos de dados de arquivamento separados (usando bancos de dados do SQL Server) para armazenamento de arquivamento para alguns ou todos os usuários, SQL Server no servidor que armazenará os dados de arquivamento.  <br/> O Arquivamento é executado nos Servidores Front-End de um pool Enterprise e Servidores Standard Edition. Não há requisitos adicionais de hardware ou software além daqueles necessários para instalar esses servidores.  <br/> |Usuário do domínio que é membro do grupo local de administradores.  <br/> |[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/>  [Plano para integrar o Skype for Business e o Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) <br/>[Requisitos do sistema para o Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) |
|**Criar a topologia interna apropriada para dar suporte ao arquivamento (apenas se não estiver usando a integração do Microsoft Exchange para todos os usuários em sua implantação)** <br/> |Execute o construtor de topologias para adicionar bancos de dados de arquivamento do Skype for Business Server (bancos de dados do SQL Server) à topologia e, em seguida, publique a topologia.  <br/> |Para definir a topologia a fim de incorporar bancos de dados de arquivamento, uma conta que é membro do grupo local de usuários.  <br/> Para publicar a topologia, uma conta que é membro do grupo Domain admins e do grupo RTCUniversalServerAdmins, e que tem permissões de controle total (leitura/gravação/modificação) no compartilhamento de arquivos a ser usado para o repositório de arquivos do Skype for Business Server (para que a topologia O construtor pode configurar as DACLs obrigatórias).  <br/> |[Adicionar bancos de dados de arquivamento a uma implantação existente no Skype for Business Server](add-archiving-databases.md) <br/> |
|**Configurar a autenticação do servidor para o servidor (somente se estiver usando a integração do Microsoft Exchange)** <br/> |Configurar servidores para habilitar a autenticação entre o Skype for Business Server e o Exchange. Recomendamos executar o **dumpster Test-CsExchangeStorageConnectivity testuser_sipUri-Folder** para validar a conectividade do armazenamento do Exchange Archiving antes de habilitar o arquivamento. <br/> |Uma conta com permissões adequadas para gerenciar certificados nos servidores.  <br/> |Gerencie autenticação servidor para servidor  <br/> |
|**Configure políticas e opções de arquivamento** <br/> |Configurar o arquivamento, incluindo se a integração do Microsoft Exchange, a política global e as políticas de usuário e de qualquer site (quando não estão sendo usadas na integração do Microsoft Exchange para todos os dados) e opções de arquivamento específicas, como dados e modo crítico exportar e descartar.  <br/> Se estiver usando a integração do Microsoft Exchange, configure as políticas de bloqueio do Exchange in-loco conforme apropriado.  <br/> |Grupo RTCUniversalServerAdmins (somente Windows PowerShell) ou atribua usuários à função CSArchivingAdministrator ou CSAdministrator.  <br/> |[Configurar opções de arquivamento para o Skype for Business Server](configure-archiving-options.md) <br/> Documentação do produto Exchange (se estiver usando a integração do Microsoft Exchange).  <br/> |
   

