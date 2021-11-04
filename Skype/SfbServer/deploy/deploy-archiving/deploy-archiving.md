---
title: Implantar arquivamento para Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 50fa535c-7347-4e33-80a3-296748ef6666
description: 'Resumo: leia este tópico para saber como implantar o arquivamento para Skype for Business Server.'
ms.openlocfilehash: e9351ed9b13b2e3bbc416f9ff3e1141c2de01a08
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60758183"
---
# <a name="deploy-archiving-for-skype-for-business-server"></a>Implantar arquivamento para Skype for Business Server
 
**Resumo:** Leia este tópico para saber como implantar o arquivamento para Skype for Business Server.
  
O arquivamento é instalado automaticamente em cada Servidor Front-End em sua implantação Skype for Business Server, mas você ainda precisa executar etapas iniciais de configuração e configuração antes de poder usá-lo. Antes de começar, certifique-se de que você está familiarizado com os conceitos em [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).
  
## <a name="deployment-checklist"></a>Lista de verificação de implantação

A configuração do arquivamento depende de qual opção de armazenamento você escolher: 
  
- Se você usar a integração Exchange microsoft para todos os usuários em sua implantação, não precisará configurar Skype for Business Server de arquivamento para seus usuários. Em vez disso, você configura Exchange In-Place políticas de Espera para dar suporte ao arquivamento para usuários que estão Exchange, com suas caixas de correio colocadas em In-Place Hold. Para obter detalhes sobre como configurar essas políticas, consulte a documentação Exchange produto.
    
- Se você não usar a integração do Microsoft Exchange para todos os usuários em sua implantação, precisará adicionar bancos de dados de arquivamento Skype for Business Server (bancos de dados SQL Server) à sua topologia, publicar a topologia atualizada e, em seguida, configurar políticas de arquivamento e configurações para seus usuários. Você pode implantar bancos de dados de arquivamento ao mesmo tempo em que implanta sua topologia inicial ou depois de ter implantado pelo menos um pool de Front-End ou Edição Standard Server. Este documento descreve como implantar bancos de dados de arquivamento adicionando-os a uma implantação existente.
    
Se você habilitar o arquivamento em um pool de Front-End ou Edição Standard Server, você deve habilita-lo para todos os outros pools de Front-End e Edição Standard Servidores em sua implantação. Isso porque os usuários cujas comunicações precisam ser arquivadas podem ser convidados a um grupo de conversação de IM ou a reuniões hospedadas em um pool diferente. Se o arquivamento não estiver habilitado no pool no qual a conversa ou a reunião está hospedada, a sessão completa não poderá ser arquivada. Nesses casos, as IMs com usuários habilitados para arquivamento ainda poderão ser arquivados, menos para arquivos de conteúdo de conferência e eventos de ingresso ou saída de conferências.
  
> [!IMPORTANT]
> Se o arquivamento for fundamental em sua organização por motivos de conformidade, certifique-se de implantar o arquivamento, configurar políticas e outras opções no nível apropriado e, em seguida, ativar o arquivamento para todos os usuários apropriados, antes de habilitar esses usuários para Skype for Business Server. 
  
A tabela a seguir fornece uma visão geral das etapas necessárias para implantar o arquivamento em uma topologia existente.
  
|**Fase**|**Etapas**|**Associações a grupos e funções**|**Documentação**|
|:-----|:-----|:-----|:-----|
|**Instalar os pré-requisitos de hardware e software** <br/> |Para usar a Exchange microsoft (usando Exchange para arquivamento de armazenamento para alguns ou todos os usuários), você precisa de uma implantação Exchange existente.  <br/> Para usar bancos de dados de arquivamento separados (usando bancos de dados SQL Server) para arquivamento de armazenamento para alguns ou todos os usuários, SQL Server no servidor que armazenará dados de arquivamento.  <br/> O arquivamento é executado em Servidores Front-End de um pool Enterprise e Edição Standard Servidores. Não há requisitos adicionais de hardware e software além daqueles para instalar esses servidores.  <br/> |Usuário do domínio que é membro do grupo local de administradores.  <br/> |[Requisitos de servidor para Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Requisitos ambientais Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/>  [Plano para integrar o Skype for Business e o Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) <br/>[Requisitos do sistema para Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) |
|**Crie a topologia interna apropriada para dar suporte ao arquivamento (somente se não estiver usando a integração Exchange Microsoft para todos os usuários em sua implantação)** <br/> |Execute o Construtor de Topologias para adicionar Skype for Business Server de arquivamento (SQL Server bancos de dados) à topologia e publique a topologia.  <br/> |Para definir uma topologia para incorporar bancos de dados de arquivamento, uma conta que é membro do grupo de usuários locais.  <br/> Para publicar a topologia, uma conta que é membro do grupo de administradores de domínio e do grupo RTCUniversalServerAdmins e que tem permissões de controle total (leitura/gravação/modificação) no compartilhamento de arquivos a ser usado para o armazenamento de arquivos do Skype for Business Server (para que o Construtor de Topologias possa configurar os DACLs necessários).  <br/> |[Adicionar bancos de dados de arquivamento a uma implantação existente no Skype for Business Server](add-archiving-databases.md) <br/> |
|**Configurar a autenticação de servidor para servidor (somente se estiver usando a integração Exchange Microsoft)** <br/> |Configure servidores para habilitar a autenticação entre Skype for Business Server e Exchange. Recomendamos executar **Test-CsExchangeStorageConnectivity testuser_sipUri -Folder Dumpster** para validar Exchange conectividade de armazenamento de arquivamento antes de habiltar o arquivamento. <br/> |Uma conta com permissões adequadas para gerenciar certificados nos servidores.  <br/> |Gerenciar autenticação de servidor para servidor  <br/> |
|**Configurar opções e políticas de arquivamento** <br/> |Configure o arquivamento, incluindo se deve usar a integração do Microsoft Exchange, a política global e quaisquer políticas de site e usuário (ao não usar a integração do Microsoft Exchange para todo o armazenamento de dados) e opções de arquivamento específicas, como modo crítico e exportação e purgação de dados.  <br/> Se estiver usando a integração Exchange Microsoft, configure Exchange In-Place de Espera conforme apropriado.  <br/> |Grupo RTCUniversalServerAdmins (somente Windows PowerShell) ou atribua usuários à função CSArchivingAdministrator ou CSAdministrator.  <br/> |[Configurar opções de arquivamento para Skype for Business Server](configure-archiving-options.md) <br/> Exchange documentação do produto (se estiver usando a integração Exchange Microsoft).  <br/> |
   

