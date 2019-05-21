---
title: Implantar Servidor de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8373c93b-92a7-4932-bc1f-00fc08955426
description: 'Resumo: Leia este tópico para saber como implantar o Skype for Business Server 2015 servidor de chat persistente.'
ms.openlocfilehash: 06cc51ccbbab193e749c2f919102d7d38fde3f56
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34273893"
---
# <a name="deploy-persistent-chat-server-in-skype-for-business-server-2015"></a>Implantar Servidor de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber como implantar o Skype for Business Server 2015 servidor de chat persistente.
  
Para implantar o servidor de chat persistente, você: 
  
- Usar o construtor de topologias para definir ou importar e publicar subseqüentemente a topologia e os componentes que você deseja implantar
    
- Preparar seu ambiente para implantar componentes persistentes do servidor de chat
    
- Instalar e configurar componentes do servidor de chat persistente para a sua implantação
    
Antes de implantar o servidor de chat persistente, você deve ler o [plano do servidor de chat persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). Os tópicos de planejamento descrevem requisitos de hardware e software, possíveis topologias e cenários de colocação. 
  
> [!NOTE] 
> O chat persistente está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019. A mesma funcionalidade está disponível no Microsoft Teams. Para obter mais informações, consulte [jornada do Skype for Business para o Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams). Se você precisar usar chats persistentes, suas opções serão migrar os usuários que exigem essa funcionalidade para o Microsoft Teams ou para continuar usando o Skype for Business Server 2015. 

## <a name="deployment-checklist"></a>Lista de verificação da implantação

Você pode implantar o servidor de chat persistente após implantar a topologia inicial, incluindo pelo menos um pool de front-end do Skype for Business Server ou um servidor do Skype for Business Standard Edition. A lista de verificação de implantação descreve as etapas básicas necessárias para implantar o servidor de chat persistente e fornece links para obter mais detalhes.
  
**Processo de implantação do servidor de chat persistente**

|**Tarefa**|**Etapas**|**Funções exigidas e associações em grupo**|**Tópicos relacionados**|
|:-----|:-----|:-----|:-----|
|**Instalar pré-requisitos de hardware e software** <br/> | No hardware que atender aos requisitos do sistema, instale o seguinte: <br/>  Nos servidores de front-end do servidor de chat persistente: <br/>  Um sistema operacional que atenda aos requisitos do sistema <br/>  Pré-requisitos de software para computadores que executam o Skype for Business Server <br/>  No servidor que hospedará o banco de dados persistente do servidor de chat: <br/>  Uma versão suportada do SQL Server <br/>  Se for necessário conformidade com o servidor de chat persistente: <br/>  SQL Server no servidor que hospedará o banco de dados de conformidade do servidor de chat persistente <br/> |Qualquer usuário que seja membro do grupo Administradores locais.  <br/> |[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [Requisitos de hardware e software para Servidor de Chat Persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md) <br/> |
|**Criar a topologia interna apropriada para dar suporte a servidor de chat persistente (e, opcionalmente, conformidade de chat persistente)** <br/> | Execute o construtor de topologias para adicionar um pool de servidores de chat persistentes à sua topologia: <br/>  Adicionar componentes persistentes do servidor de chat à topologia <br/>  Criar um banco de dados SQL Server para o repositório persistente do servidor de chat (e um SQL Server de backup para recuperação de desastres) <br/>  Definir um novo repositório de arquivos do Skype for Business ou usar um repositório de arquivos existente do Skype for Business para arquivos do servidor de chat persistente <br/>  Associar o pool do servidor do Skype for Business que pode rotear solicitações para este pool de servidores de chat persistente <br/>  Se a conformidade com Chat Persistente for necessária: <br/>  Adicionar repositório de conformidade de chat persistente <br/>  Clique na caixa de seleção definição do pool de servidores de chat persistentes para habilitar a conformidade <br/>  Publique a topologia. <br/>  Se você instalar o servidor de chat persistente na edição Standard, o nome de domínio totalmente qualificado (FQDN) do pool do servidor de chat persistente deve coincidir com o servidor Standard Edition e os bancos de dados do SQL Server são posicionados na instância do SQL Server Express no padrão Servidor de edição <br/> |Para definir uma topologia, uma canta membro do grupo de usuários local.  <br/> Para publicar a topologia, uma conta que seja membro do grupo Domain admins e do grupo RTCUniversalServerAdmins, e o usuário também deve ter permissões de controle total (ler/gravar/modificar) no repositório de arquivos do Skype for Business para arquivos persistentes do servidor de chat (so Esse construtor de topologias pode configurar as DACLs obrigatórias).  <br/> |[Criar e publicar uma nova topologia no Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md) <br/> [Adicionar um servidor de chat persistente à sua topologia do Skype for Business Server 2015](add-persistent-chat-server.md) <br/> |
|**Implantar Servidor de Chat Persistente** <br/> | Execute a instalação do Skype for Business Server em todos os computadores que executam o servidor de chat persistente. A configuração do servidor de chat persistente está integrada ao assistente de implantação do Skype for Business Server que fornece as instruções a seguir: <br/>  Implantar repositório de gerenciamento local <br/>  Instalar serviços de chat persistente <br/>  Solicitar e assinar certificados <br/>  Executar e iniciar os serviços <br/> |Qualquer usuário que seja membro do grupo Administradores locais.  <br/> |[Implantar um Servidor de Chat persistente no Skype for Business Server 2015](deploy-persistent-chat-server.md) <br/> |
|**Criar um administrador de Chat Persistente** <br/> |Adicionar usuários ao grupo de segurança CsPersistentChatAdministrator.  <br/> |Qualquer usuário que seja membro dos administradores de domínio.  <br/> |[Criar um administrador de Chat Persistente no Skype for Business Server 2015](create-a-persistent-chat-administrator.md) <br/> |
|**Configurar o Servidor de Chat Persistente** <br/> | Configurar usuários: <br/>  O usuário deve ser habilitado pela política para acessar o servidor de chat persistente. Por padrão, a política está desativada para todos os usuários e pode ser definida nos escopos global/site/pool/usuário. <br/>  Definir configurações <br/> |O usuário deve ser membro do CsPersistentChatAdministrator. Para alterar a política, o usuário deve estar no CsUserAdministrator, no mínimo.  <br/> |[Gerenciar Servidor de Chat Persistente no Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md) <br/> |
   

