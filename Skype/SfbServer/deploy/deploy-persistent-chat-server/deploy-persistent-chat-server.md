---
title: Implantar Servidor de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8373c93b-92a7-4932-bc1f-00fc08955426
description: 'Resumo: Leia este tópico para saber como implantar o Skype para Business Server 2015 Persistent Chat Server.'
ms.openlocfilehash: 2b88d20437a85c9a634bf8a156a3dcec214c60fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894462"
---
# <a name="deploy-persistent-chat-server-in-skype-for-business-server-2015"></a>Implantar Servidor de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber como implantar o Skype para Business Server 2015 Persistent Chat Server.
  
Para implantar o servidor de Chat persistente, você: 
  
- Use o construtor de topologias para definir, ou importar e subsequentemente publicar sua topologia e os componentes que você deseja implantar
    
- Prepare seu ambiente de implantação de componentes do servidor de Chat persistente
    
- Instalar e configurar componentes de servidor de Chat persistente para sua implantação
    
Antes de implantar o servidor de Chat persistente, você deve ler [Planejar Persistent Chat Server in Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). Os tópicos de planejamento descrevem requisitos de hardware e software, possíveis topologias e cenários de colocação. 
  
> [!NOTE] 
> Bate-papo persistente está disponível no Skype para Business Server 2015, mas não é mais suportado no Skype para Business Server 2019. A mesma funcionalidade está disponível em equipes. Para obter mais informações, consulte [jornada do Skype para negócios às equipes da Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Se você precisar utilizar o chat persistente, suas opções são para migrar tanto os usuários que requerem essa funcionalidade para equipes ou para continuar usando o Skype para Business Server 2015. 

## <a name="deployment-checklist"></a>Lista de verificação da implantação

Você pode implantar o servidor de Chat persistente após implantar a topologia inicial, incluindo pelo menos um Skype para pool de negócios servidor Front-End ou um Skype para negócios Standard Edition Server. A lista de verificação de implantação descreve as etapas básicas necessárias para implantar o servidor de Chat persistente e fornece links para obter mais detalhes.
  
**Processo de implantação do servidor de bate-papo persistente**

|**Tarefa**|**Etapas**|**Funções exigidas e associações em grupo**|**Tópicos relacionados**|
|:-----|:-----|:-----|:-----|
|**Instalar pré-requisitos de hardware e software** <br/> | No hardware que atender aos requisitos do sistema, instale o seguinte: <br/>  Sobre o Persistent Chat servidores de Front-End do servidor: <br/>  Um sistema operacional que atenda aos requisitos do sistema <br/>  Pré-requisitos de software para computadores que executam o Skype para Business Server <br/>  No servidor que hospedará o banco de dados do servidor de Chat persistente: <br/>  Uma versão suportada do SQL Server <br/>  Se a conformidade Persistent Chat Server for necessária: <br/>  SQL Server no servidor que hospedará o banco de dados de conformidade do servidor de Chat persistente <br/> |Qualquer usuário que seja membro do grupo Administradores locais.  <br/> |[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [Requisitos de hardware e software para Servidor de Chat Persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md) <br/> |
|**Criar a topologia interna apropriada para dar suporte a Persistent Chat Server (e, opcionalmente, conformidade de Chat persistente)** <br/> | Execute o construtor de topologias para adicionar um pool do servidor de Chat persistente à sua topologia: <br/>  Adicione componentes de servidor de Chat persistente à topologia <br/>  Criar um banco de dados do SQL Server para o repositório de servidor de Chat persistente (e um servidor SQL de backup para recuperação de desastre) <br/>  Definir um novo Skype para negócios File Store ou use um Skype existente para o repositório de arquivos corporativos para arquivos do servidor de Chat persistente <br/>  Associar o Skype para pool de servidores de negócios que pode rotear solicitações para este pool de servidor de Chat persistente <br/>  Se a conformidade com Chat Persistente for necessária: <br/>  Adicionar repositório de conformidade de bate-papo persistente <br/>  Clique na caixa de seleção de definição de pool Persistent Chat Server para habilitar a conformidade <br/>  Publique a topologia. <br/>  Se você instalar o servidor de Chat persistente no Standard Edition, o nome de domínio totalmente qualificado (FQDN) do pool do servidor de Chat persistente deve coincidir com o servidor Standard Edition e os bancos de dados do SQL Server são colocados na instância do SQL Server Express no padrão Servidor Edition <br/> |Para definir uma topologia, uma canta membro do grupo de usuários local.  <br/> Para publicar a topologia, uma conta que seja membro do grupo Administradores de domínio e grupo RTCUniversalServerAdmins e o usuário também deve ter permissões de controle total (leitura/gravação/modificar) sobre o Skype para negócios File Store para arquivos do servidor de Chat persistente (caso Esse construtor de topologia pode configurar as DACLs necessárias).  <br/> |[Criar e publicar uma nova topologia no Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md) <br/> [Adicionar servidor de Chat persistente à sua Skype para a topologia de negócios Server 2015](add-persistent-chat-server.md) <br/> |
|**Implantar Servidor de Chat Persistente** <br/> | Execute o Skype para a instalação do servidor de negócios em todos os computadores executando o servidor de Chat persistente. A configuração do servidor de Chat persistente é integrada ao Skype para o Assistente de implantação de servidor de negócios que fornece as seguintes instruções: <br/>  Implantar repositório de gerenciamento local <br/>  Instalar os serviços de Chat persistente <br/>  Solicitar e assinar certificados <br/>  Executar e iniciar os serviços <br/> |Qualquer usuário que seja membro do grupo Administradores locais.  <br/> |[Implantar um Servidor de Chat persistente no Skype for Business Server 2015](deploy-persistent-chat-server.md) <br/> |
|**Criar um administrador de Chat Persistente** <br/> |Adicionar usuários ao grupo de segurança CsPersistentChatAdministrator.  <br/> |Qualquer usuário que seja membro dos administradores de domínio.  <br/> |[Criar um administrador de Chat Persistente no Skype for Business Server 2015](create-a-persistent-chat-administrator.md) <br/> |
|**Configurar o Servidor de Chat Persistente** <br/> | Configurar usuários: <br/>  Usuário tem de ser habilitada por política para acessar o servidor de Chat persistente. Por padrão, a política está desativada para todos os usuários e pode ser definida nos escopos global/site/pool/usuário. <br/>  Definir configurações <br/> |O usuário deve ser membro do CsPersistentChatAdministrator. Para alterar a política, o usuário deve estar no CsUserAdministrator, no mínimo.  <br/> |[Gerenciar Servidor de Chat Persistente no Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md) <br/> |
   

