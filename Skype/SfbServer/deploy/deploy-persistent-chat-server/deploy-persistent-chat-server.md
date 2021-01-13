---
title: Implantar Servidor de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8373c93b-92a7-4932-bc1f-00fc08955426
description: 'Resumo: Leia este tópico para saber como implantar o Skype for Business Server 2015 Persistent Chat Server.'
ms.openlocfilehash: 60dbabc84e278f6add3b7de408787f4969a164a7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830471"
---
# <a name="deploy-persistent-chat-server-in-skype-for-business-server-2015"></a>Implantar Servidor de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber como implantar o Servidor de Chat Persistente do Skype for Business Server 2015.
  
Para implantar o Servidor de Chat Persistente, você: 
  
- Use o Construtor de Topologias para definir ou importar e publicar posteriormente sua topologia e os componentes que você deseja implantar
    
- Preparar seu ambiente para implantar componentes do Servidor de Chat Persistente
    
- Instalar e configurar componentes do Servidor de Chat Persistente para sua implantação
    
Antes de implantar o Servidor de Chat Persistente, você deve ler Plano para Servidor de [Chat Persistente no Skype for Business Server 2015.](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md) Os tópicos de planejamento descrevem requisitos de hardware e software, possíveis topologias e cenários de colocação. 
  
> [!NOTE] 
> O chat persistente está disponível no Skype for Business Server 2015, mas não é mais suportado no Skype for Business Server 2019. A mesma funcionalidade está disponível no Teams. Para saber mais, confira [Como começar a atualizar o Microsoft Teams.](/microsoftteams/upgrade-start-here) Se você precisar usar o chat persistente, suas opções são migrar os usuários que exigem essa funcionalidade para o Teams ou continuar usando o Skype for Business Server 2015. 

## <a name="deployment-checklist"></a>Lista de verificação de implantação

Você pode implantar o Servidor de Chat Persistente depois de implantar sua topologia inicial, incluindo pelo menos um pool de Front-End do Skype for Business Server ou um Servidor Skype for Business Standard Edition. A lista de verificação de implantação descreve as etapas básicas necessárias para implantar o Servidor de Chat Persistente e fornece links para mais detalhes.
  
**Processo de implantação do Servidor de Chat Persistente**

|**Tarefa**|**Etapas**|**Funções exigidas e associações em grupo**|**Tópicos relacionados**|
|:-----|:-----|:-----|:-----|
|**Instalar os pré-requisitos de hardware e software** <br/> | No hardware que atender aos requisitos do sistema, instale o seguinte: <br/>  Nos Servidores front-end do Servidor de Chat Persistente: <br/>  Um sistema operacional que atenda aos requisitos do sistema <br/>  Pré-requisitos de software para computadores que executam o Skype for Business Server <br/>  No servidor que hospedará o banco de dados do Servidor de Chat Persistente: <br/>  Uma versão suportada do SQL Server <br/>  Se a conformidade com o Servidor de Chat Persistente for necessária: <br/>  SQL Server no servidor que hospedará o banco de dados de conformidade do Servidor de Chat Persistente <br/> |Qualquer usuário que seja membro do grupo Administradores locais.  <br/> |[Requisitos de servidor para o Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Requisitos ambientais do Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [Requisitos de hardware e software para o Servidor de Chat Persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md) <br/> |
|**Criar a topologia interna apropriada para dar suporte ao Servidor de Chat Persistente (e, opcionalmente, à conformidade de Chat Persistente)** <br/> | Execute o Construtor de Topologias para adicionar um pool de Servidor de Chat Persistente à sua topologia: <br/>  Adicionar componentes do Servidor de Chat Persistente à topologia <br/>  Criar um banco de dados do SQL Server para o armazenamento do Servidor de Chat Persistente (e um SQL Server de backup para recuperação de desastres) <br/>  Definir um novo Armazenamento de Arquivos do Skype for Business ou usar um Armazenamento de Arquivos do Skype for Business existente para arquivos do Servidor de Chat Persistente <br/>  Associar o pool do Skype for Business Server que pode rotear solicitações para este pool de Servidor de Chat Persistente <br/>  Se a conformidade com o Chat Persistente for necessária: <br/>  Adicionar Armazenamento de Conformidade de Chat Persistente <br/>  Clique na caixa de seleção de definição do pool do Servidor de Chat Persistente para habilenciar a conformidade <br/>  Publique a topologia. <br/>  Se você instalar o Servidor de Chat Persistente no Standard Edition, o FQDN (nome de domínio totalmente qualificado) do pool de Servidor de Chat Persistente deverá corresponder ao servidor Standard Edition e os bancos de dados do SQL Server serão alocados na instância do SQL Server Express no servidor Standard Edition <br/> |Para definir uma topologia, uma canta membro do grupo de usuários local  <br/> Para publicar a topologia, uma conta que seja membro do grupo Administradores de Domínio e do grupo RTCUniversalServerAdmins, e o usuário também deve ter permissões de controle total (leitura/gravação/modificação) no Armazenamento de Arquivos do Skype for Business para arquivos do Servidor de Chat Persistente (para que o Construtor de Topologias possa configurar os DACLs necessários).  <br/> |[Criar e publicar nova topologia no Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md) <br/> [Adicionar Servidor de Chat Persistente à sua topologia do Skype for Business Server 2015](add-persistent-chat-server.md) <br/> |
|**Implantar Servidor de Chat Persistente** <br/> | Execute a configuração do Skype for Business Server em todos os computadores que executam o Servidor de Chat Persistente. A configuração do Servidor de Chat Persistente está integrada ao assistente de Implantação do Skype for Business Server que fornece as seguintes instruções: <br/>  Implantar repositório de gerenciamento local <br/>  Instalar serviços de Chat Persistente <br/>  Solicitar e assinar certificados <br/>  Executar e iniciar os serviços <br/> |Qualquer usuário que seja membro do grupo Administradores locais.  <br/> |[Implantar Servidor de Chat Persistente no Skype for Business Server 2015](deploy-persistent-chat-server.md) <br/> |
|**Criar um administrador de Chat Persistente** <br/> |Adicionar usuários ao grupo de segurança CsPersistentChatAdministrator.  <br/> |Qualquer usuário que seja membro dos administradores de domínio  <br/> |[Criar um administrador de Chat Persistente no Skype for Business Server 2015](create-a-persistent-chat-administrator.md) <br/> |
|**Configurar o Servidor de Chat Persistente** <br/> | Configurar usuários: <br/>  O usuário deve ser habilitado pela política para acessar o Servidor de Chat Persistente. Por padrão, a política está desativada para todos os usuários e pode ser definida nos escopos global/site/pool/usuário. <br/>  Definir configurações <br/> |O usuário deve ser membro do CsPersistentChatAdministrator. Para alterar a política, o usuário deve estar no CsUserAdministrator, no mínimo.  <br/> |[Gerenciar Servidor de Chat Persistente no Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md) <br/> |
   

