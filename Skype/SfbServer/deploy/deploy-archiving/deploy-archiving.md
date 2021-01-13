---
title: Implantar arquivamento para o Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50fa535c-7347-4e33-80a3-296748ef6666
description: 'Resumo: Leia este tópico para saber como implantar o arquivamento para o Skype for Business Server.'
ms.openlocfilehash: 32b25b373bd5399928d5e5eaed063c194942f697
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825211"
---
# <a name="deploy-archiving-for-skype-for-business-server"></a>Implantar arquivamento para o Skype for Business Server
 
**Resumo:** Leia este tópico para saber como implantar o arquivamento para o Skype for Business Server.
  
O arquivamento é instalado automaticamente em cada Servidor Front End em sua implantação do Skype for Business Server, mas você ainda precisa executar as etapas iniciais de instalação e configuração para poder usá-lo. Antes de começar, certifique-se de estar familiarizado com os conceitos no Plano de arquivamento [no Skype for Business Server.](../../plan-your-deployment/archiving/archiving.md)
  
## <a name="deployment-checklist"></a>Lista de verificação de implantação

A maneira como você configura o arquivamento depende de qual opção de armazenamento você escolher: 
  
- Se você usar a integração com o Microsoft Exchange para todos os usuários em sua implantação, não precisará configurar as políticas de arquivamento do Skype for Business Server para seus usuários. Em vez disso, você configura as In-Place de Espera do Exchange para dar suporte ao arquivamento para usuários que estão no Exchange, com suas caixas de correio colocadas em In-Place Espera. Para obter detalhes sobre como configurar essas políticas, consulte a documentação do produto do Exchange.
    
- Se você não usar a integração do Microsoft Exchange para todos os usuários em sua implantação, será necessário adicionar os bancos de dados de arquivamento do Skype for Business Server (bancos de dados do SQL Server) à sua topologia, publicar a topologia atualizada e configurar as políticas e configurações de arquivamento para seus usuários. Você pode implantar bancos de dados de arquivamento ao mesmo tempo em que implanta sua topologia inicial ou depois de implantar pelo menos um pool de Front-End ou Servidor Standard Edition. Este documento descreve como implantar bancos de dados de arquivamento adicionando-os a uma implantação existente.
    
Se você habilitar o arquivamento em um pool de front-end ou servidor Standard Edition, deverá habilita-lo para todos os outros pools de Front-End e Servidores Standard Edition em sua implantação. Isso porque os usuários cujas comunicações precisam ser arquivadas podem ser convidados a um grupo de conversação de IM ou a reuniões hospedadas em um pool diferente. Se o arquivamento não estiver habilitado no pool no qual a conversa ou a reunião está hospedada, a sessão completa não poderá ser arquivada. Nesses casos, as IMs com usuários habilitados para arquivamento ainda poderão ser arquivados, menos para arquivos de conteúdo de conferência e eventos de ingresso ou saída de conferências.
  
> [!IMPORTANT]
> Se o arquivamento for fundamental em sua organização por motivos de conformidade, certifique-se de implantar o arquivamento, configurar políticas e outras opções no nível apropriado e, em seguida, ativar o arquivamento para todos os usuários apropriados, antes de habilitar esses usuários para o Skype for Business Server. 
  
A tabela a seguir fornece uma visão geral das etapas necessárias para implantar o arquivamento em uma topologia existente.
  
|**Fase**|**Etapas**|**Associações a grupos e funções**|**Documentação**|
|:-----|:-----|:-----|:-----|
|**Instalar os pré-requisitos de hardware e software** <br/> |Para usar a integração com o Microsoft Exchange (usando o Exchange para armazenamento de arquivamento para alguns ou todos os usuários), você precisa de uma implantação existente do Exchange.  <br/> Para usar bancos de dados de arquivamento separados (usando bancos de dados do SQL Server) para o armazenamento de arquivamento de alguns ou todos os usuários, o SQL Server no servidor que armazenará os dados de arquivamento.  <br/> O arquivamento é executado em servidores front-end de um pool Enterprise e servidores Standard Edition. Não há requisitos adicionais de hardware e software além daqueles para instalar esses servidores.  <br/> |Usuário do domínio que é membro do grupo local de administradores.  <br/> |[Requisitos de servidor para o Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Requisitos ambientais do Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/>  [Plano para integrar o Skype for Business e o Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) <br/>[Requisitos do sistema para o Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) |
|**Crie a topologia interna apropriada para dar suporte ao arquivamento (somente se não estiver usando a integração com o Microsoft Exchange para todos os usuários em sua implantação)** <br/> |Execute o Construtor de Topologias para adicionar bancos de dados de arquivamento do Skype for Business Server (bancos de dados do SQL Server) à topologia e publique a topologia.  <br/> |Para definir uma topologia para incorporar bancos de dados de arquivamento, uma conta que é membro do grupo de usuários locais.  <br/> Para publicar a topologia, uma conta que seja membro do grupo de administradores de domínio e do grupo RTCUniversalServerAdmins e que tenha permissões de controle total (leitura/gravação/modificação) no compartilhamento de arquivos a ser usado para o armazenamento de arquivos do Skype for Business Server (para que o Construtor de Topologias possa configurar os DACLs necessários).  <br/> |[Adicionar bancos de dados de arquivamento a uma implantação existente no Skype for Business Server](add-archiving-databases.md) <br/> |
|**Configurar a autenticação de servidor para servidor (somente se estiver usando a integração com o Microsoft Exchange)** <br/> |Configurar servidores para habilitar a autenticação entre o Skype for Business Server e o Exchange. Recomendamos executar **Test-CsExchangeStorageConnectivity testuser_sipUri -Folder Dumpster** para validar a conectividade de armazenamento de arquivamento do Exchange antes de habiltar o arquivamento. <br/> |Uma conta com permissões adequadas para gerenciar certificados nos servidores.  <br/> |Gerenciar autenticação de servidor para servidor  <br/> |
|**Configurar políticas e opções de arquivamento** <br/> |Configure o arquivamento, incluindo se será usada a integração com o Microsoft Exchange, a política global e quaisquer políticas de site e usuário (quando não estiver usando a integração com o Microsoft Exchange para todo o armazenamento de dados) e opções de arquivamento específicas, como modo crítico e exportação e purgação de dados.  <br/> Se estiver usando a integração com o Microsoft Exchange, configure as In-Place de Espera do Exchange conforme apropriado.  <br/> |Grupo RTCUniversalServerAdmins (somente Windows PowerShell) ou atribua usuários à função CSArchivingAdministrator ou CSAdministrator.  <br/> |[Configurar opções de arquivamento para o Skype for Business Server](configure-archiving-options.md) <br/> Documentação do produto do Exchange (se estiver usando a integração com o Microsoft Exchange).  <br/> |
   

