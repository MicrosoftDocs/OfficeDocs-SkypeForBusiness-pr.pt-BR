---
title: Implantar o Servidor de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8373c93b-92a7-4932-bc1f-00fc08955426
description: 'Resumo: leia este tópico para saber como implantar o Skype for Business Server de Chat Persistente 2015.'
ms.openlocfilehash: 2fa97848809a05f87a700d71decd2c61be26bb70
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759003"
---
# <a name="deploy-persistent-chat-server-in-skype-for-business-server-2015"></a>Implantar o Servidor de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber como implantar o Skype for Business Server de Chat Persistente 2015.
  
Para implantar o Servidor de Chat Persistente, você: 
  
- Use o Construtor de Topologias para definir ou importar e publicar subsequentemente sua topologia e os componentes que você deseja implantar
    
- Preparar seu ambiente para implantar componentes do Servidor de Chat Persistente
    
- Instalar e configurar componentes do Servidor de Chat Persistente para sua implantação
    
Antes de implantar o Servidor de Chat Persistente, leia Plan for Persistent Chat Server no Skype for Business Server [2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). Os tópicos de planejamento descrevem requisitos de hardware e software, possíveis topologias e cenários de colocação. 
  
> [!NOTE] 
> O chat persistente está disponível no Skype for Business Server 2015, mas não tem mais suporte no Skype for Business Server 2019. A mesma funcionalidade está disponível no Teams. Para obter mais informações, consulte [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Se você precisar usar o chat persistente, suas opções são migrar usuários que exigem essa funcionalidade para Teams ou continuar usando o Skype for Business Server 2015. 

## <a name="deployment-checklist"></a>Lista de verificação de implantação

Você pode implantar o Servidor de Chat Persistente depois de implantar sua topologia inicial, incluindo pelo menos um pool Skype for Business Server front-end ou um Skype for Business Edição Standard Server. A lista de verificação de implantação descreve as etapas básicas necessárias para implantar o Servidor de Chat Persistente e fornece links para obter mais detalhes.
  
**Processo de implantação do servidor de chat persistente**

|**Tarefa**|**Etapas**|**Funções exigidas e associações em grupo**|**Tópicos relacionados**|
|:-----|:-----|:-----|:-----|
|**Instalar os pré-requisitos de hardware e software** <br/> | No hardware que atender aos requisitos do sistema, instale o seguinte: <br/>  Nos servidores front-end do Servidor de Chat Persistente: <br/>  Um sistema operacional que atenda aos requisitos do sistema <br/>  Pré-requisitos de software para computadores que executam Skype for Business Server <br/>  No servidor que hospedará o banco de dados do Servidor de Chat Persistente: <br/>  Uma versão com suporte do SQL Server <br/>  Se a conformidade do Servidor de Chat Persistente for necessária: <br/>  SQL Server no servidor que hospedará o banco de dados de conformidade do Servidor de Chat Persistente <br/> |Qualquer usuário que seja membro do grupo Administradores locais.  <br/> |[Requisitos de servidor para Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Requisitos ambientais Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [Requisitos de hardware e software para o Servidor de Chat Persistente Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md) <br/> |
|**Crie a topologia interna apropriada para dar suporte ao Servidor de Chat Persistente (e, opcionalmente, conformidade de Chat Persistente)** <br/> | Execute o Construtor de Topologias para adicionar um pool de Servidor de Chat Persistente à sua topologia: <br/>  Adicionar componentes do Servidor de Chat Persistente à topologia <br/>  Criar um SQL Server de dados para o armazenamento do Servidor de Chat Persistente (e um backup SQL Server para recuperação de desastres) <br/>  Definir um novo Skype for Business de arquivos ou usar um armazenamento de arquivos Skype for Business existente para arquivos do Servidor de Chat Persistente <br/>  Associar o pool Skype for Business Server que pode rotear solicitações para este pool de Servidores de Chat Persistente <br/>  Se a conformidade do Chat Persistente for necessária: <br/>  Adicionar o Armazenamento de Conformidade de Chat Persistente <br/>  Clique na caixa de seleção Definição do pool do Servidor de Chat Persistente para habilenciar a conformidade <br/>  Publique a topologia. <br/>  Se você instalar o Servidor de Chat Persistente no Edição Standard, o FQDN (nome de domínio totalmente qualificado) do pool do Servidor de Chat Persistente deverá corresponder ao servidor Edição Standard e os bancos de dados do SQL Server serão alocados na instância SQL Server Express no servidor Edição Standard <br/> |Para definir uma topologia, uma canta membro do grupo de usuários local  <br/> Para publicar a topologia, uma conta que é membro do grupo Administradores de Domínio e do grupo RTCUniversalServerAdmins, e o usuário também deve ter permissões de controle total (leitura/gravação/modificação) no armazenamento de arquivos do Skype for Business para arquivos do Servidor de Chat Persistente (para que o Construtor de Topologias possa configurar os DACLs necessários).  <br/> |[Criar e publicar nova topologia no Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md) <br/> [Adicionar Servidor de Chat Persistente à topologia Skype for Business Server 2015](add-persistent-chat-server.md) <br/> |
|**Implantar Servidor de Chat Persistente** <br/> | Execute a Skype for Business Server em todos os computadores que executam o Servidor de Chat Persistente. A configuração do Servidor de Chat Persistente é integrada ao assistente de implantação Skype for Business Server que fornece as seguintes instruções: <br/>  Implantar repositório de gerenciamento local <br/>  Instalar serviços de Chat Persistente <br/>  Solicitar e assinar certificados <br/>  Executar e iniciar os serviços <br/> |Qualquer usuário que seja membro do grupo Administradores locais.  <br/> |[Implantar o Servidor de Chat Persistente no Skype for Business Server 2015](deploy-persistent-chat-server.md) <br/> |
|**Criar um administrador de Chat Persistente** <br/> |Adicionar usuários ao grupo de segurança CsPersistentChatAdministrator.  <br/> |Qualquer usuário que seja membro dos administradores de domínio  <br/> |[Criar um administrador de Chat Persistente no Skype for Business Server 2015](create-a-persistent-chat-administrator.md) <br/> |
|**Configurar o Servidor de Chat Persistente** <br/> | Configurar usuários: <br/>  O usuário precisa ser habilitado pela política para acessar o Servidor de Chat Persistente. Por padrão, a política está desativada para todos os usuários e pode ser definida nos escopos global/site/pool/usuário. <br/>  Definir configurações <br/> |O usuário deve ser membro do CsPersistentChatAdministrator. Para alterar a política, o usuário deve estar no CsUserAdministrator, no mínimo.  <br/> |[Gerenciar o Servidor de Chat Persistente no Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md) <br/> |
   

