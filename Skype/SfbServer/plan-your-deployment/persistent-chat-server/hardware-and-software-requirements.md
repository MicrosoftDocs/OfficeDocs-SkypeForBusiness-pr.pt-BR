---
title: Requisitos de hardware e software para o Servidor de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/19/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: 'Resumo: leia este tópico para saber mais sobre os requisitos de hardware e software para o Servidor de Chat Persistente no Skype for Business Server 2015.'
ms.openlocfilehash: d4609d557e5c55b680c4c0761f24cc4f320afcbd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095105"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Requisitos de hardware e software para o Servidor de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber mais sobre os requisitos de hardware e software para o Servidor de Chat Persistente no Skype for Business Server 2015.
  
O Servidor de Chat Persistente pode ser instalado com o Skype for Business Server 2015 Enterprise Edition ou o Standard Edition. Os requisitos dependem de qual edição do Skype for Business Server 2015 você instalou e dos requisitos de desempenho da sua empresa. O Enterprise Edition pode suportar até 80.000 usuários simultâneos; O Standard Edition pode suportar até 20.000 usuários simultâneos. O Chat Persistente consiste em um componente front-end, bem como um componente de banco de dados SQL back-end.
  
Antes de implantar o Servidor de Chat Persistente, você deve garantir que os seguintes requisitos de hardware e software sejam atendidos:
  
- Hardware que atende aos requisitos mínimos para dar suporte ao Skype for Business Server 2015, Servidor de Chat Persistente, servidores de banco de dados e servidores de arquivos. Para obter mais informações, consulte [Requisitos de servidor para Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Software de banco de dados e sistema operacional com suporte.
    
    Para obter detalhes sobre sistemas operacionais e software de banco de dados com suporte e requisitos de atualização do Windows, consulte Requisitos de servidor para [Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Servidor Front-End do Skype for Business Server 2015. O Servidor Front-End é a base para o roteamento sip (Protocolo de Iniciação de Sessão), o que torna possível a comunicação entre computadores que executam o Servidor de Chat Persistente e a funcionalidade de Chat Persistente. 
    
- Software de en fila de mensagens. Usado pelo Servidor de Chat Persistente e pelo serviço de Conformidade de Chat Persistente, se implantado.
    
As seções a seguir descrevem os requisitos específicos para o Servidor de Chat Persistente e o banco de dados que armazena os dados de Chat Persistente.

> [!NOTE] 
> O chat persistente está disponível no Skype for Business Server 2015, mas não tem mais suporte no Skype for Business Server 2019. A mesma funcionalidade está disponível no Teams. Para obter mais informações, consulte [Como começar com a atualização do Microsoft Teams.](/microsoftteams/upgrade-start-here) Se você precisar usar o chat persistente, suas opções são migrar usuários que exigem essa funcionalidade para o Teams ou continuar usando o Skype for Business Server 2015. 
  
## <a name="front-end-server-requirements"></a>Requisitos do Servidor Front-End

Os requisitos do Servidor Front-End dependem se você está implantando o Servidor de Chat Persistente com o Skype for Business Server 2015 Enterprise Edition ou Standard Edition.
  
- Se você estiver implantando o Servidor de Chat Persistente com o Skype for Business Server 2015 Enterprise Edition, poderá implantar o Servidor front-end do Servidor de Chat Persistente em um ou mais computadores autônomos no pool do Enterprise Edition. Não é possível colocar os Servidores front-end de Chat Persistente no Servidor Front-End do Skype for Business Server 2015. 
    
    Um único Servidor Front-End do Servidor de Chat Persistente pode dar suporte a 20.000 usuários ativos. Você pode ter um pool de Servidor de Chat Persistente com até 4 front ends ativos, dando suporte a um total de 80.000 usuários simultâneos. 
    
- Se você estiver implantando o Servidor de Chat Persistente com o Skype for Business Server 2015 Standard Edition, poderá colocar o Chat Persistente com o Servidor Front-End. Essa implantação de servidor único pode dar suporte a até 20.000 usuários. 
    
## <a name="persistent-chat-server-database-requirements"></a>Requisitos de banco de dados do Servidor de Chat Persistente

O Servidor de Chat Persistente SQL Server software de banco de dados para armazenar o histórico e o conteúdo da sala de chat, os dados de configuração, os dados de provisionamento do usuário e outros metadados relevantes. Opcionalmente, ele usa o banco de dados de Conformidade de Chat Persistente para armazenar dados de conformidade. Os bancos de dados de Chat Persistente podem ser alocados na mesma SQL Server, ou até mesmo na mesma instância SQL, como os bancos de dados back-end. 
  
- Se você estiver instalando o Servidor de Chat Persistente com o Skype for Business Server 2015 Enterprise Edition, para garantir um desempenho ideal, é recomendável instalar o armazenamento de arquivos de Chat Persistente.
    
- Se você estiver instalando o Servidor de Chat Persistente com a edição Standard do Skype for Business Server 2015, poderá implantar o Servidor Back-End do Armazenamento de Chat Persistente na instância SQL Server Express local.
    
- O banco de dados de Chat Persistente (mgc) e o banco de dados de conformidade (mgccomp) podem estar localizados na mesma instância do SQL Server ou em servidores SQL diferentes.
    
Para preparar uma plataforma de servidor de banco de dados, certifique-se de que cada computador atenda aos requisitos de hardware e instale o software de pré-requisito. A plataforma de servidor para servidores de banco de dados de Chat Persistente requer o mesmo hardware do servidor de banco de dados back-end do Skype for Business Server 2015. Para obter detalhes, consulte [Requisitos de servidor para Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
  
No servidor de banco de dados, certifique-se de que um dos seguintes aplicativos de software está instalado:

- Microsoft SQL Server 2017 com o service pack mais recente.

- Microsoft SQL Server 2016 com Service Pack 1 e você deve executar com o Skype for Business Server Cumulative Update 7 ou versões posteriores. Recomendamos executar SQL Server 2016 com o service pack mais recente. Para obter detalhes sobre como instalar o Microsoft SQL Server 2016, consulte [Install SQL Server 2016](/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016).

- Microsoft SQL Server 2014 e você deve executar com o Skype for Business Server Cumulative Update 6 ou versões posteriores. Recomendamos a execução SQL Server 2014 com o service pack mais recente. Para obter detalhes sobre como instalar o Microsoft SQL Server 2014, consulte [Install SQL Server 2014](/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014).

- Microsoft SQL Server 2012 (edição de 64 bits) e recomendamos a execução com o service pack mais recente. Para obter detalhes sobre como instalar o Microsoft SQL Server 2012, consulte [Install SQL Server 2012](/previous-versions/sql/sql-server-2012/bb500395(v=sql.110)).

## <a name="persistent-chat-server-certificate-requirements"></a>Requisitos de certificado do Servidor de Chat Persistente

Para obter detalhes sobre como adquirir certificados, criar o banco de dados SQL Server e criar armazenamentos de arquivos, consulte [Deploy Skype for Business Server 2015](../../deploy/deploy.md). 
  
## <a name="for-more-information"></a>Para saber mais

Para obter mais informações sobre requisitos de hardware e software, consulte os seguintes tópicos:
  
- [Requisitos de servidor para o Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [Requisitos ambientais para o Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
