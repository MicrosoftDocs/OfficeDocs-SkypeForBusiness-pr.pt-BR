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
description: 'Resumo: Leia este tópico para saber mais sobre os requisitos de hardware e software para o Servidor de Chat Persistente no Skype for Business Server 2015.'
ms.openlocfilehash: 32ba0d94679e6f326fa1821cbe3401d031854037
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834531"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Requisitos de hardware e software para o Servidor de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber mais sobre os requisitos de hardware e software para o Servidor de Chat Persistente no Skype for Business Server 2015.
  
O Servidor de Chat Persistente pode ser instalado com o Skype for Business Server 2015 Enterprise Edition ou Standard Edition. Os requisitos dependem de qual edição do Skype for Business Server 2015 você instalou e dos requisitos de desempenho da sua empresa. O Enterprise Edition pode dar suporte a até 80.000 usuários simultâneos; O Standard Edition pode dar suporte a até 20.000 usuários simultâneos. O Chat Persistente consiste em um componente front-end, bem como um componente de banco de dados SQL back-end.
  
Antes de implantar o Servidor de Chat Persistente, você deve garantir que os seguintes requisitos de hardware e software sejam atendidos:
  
- Hardware que atenda aos requisitos mínimos para dar suporte ao Skype for Business Server 2015, Servidor de Chat Persistente, servidores de banco de dados e servidores de arquivos. Para obter mais informações, [consulte Requisitos de servidor para o Skype for Business Server 2015.](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- Software de sistema operacional e banco de dados com suporte.
    
    Para obter detalhes sobre sistemas operacionais suportados e software de banco de dados e requisitos de atualização do Windows, consulte Requisitos de servidor para [o Skype for Business Server 2015.](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- Servidor front-end do Skype for Business Server 2015. O Servidor front-end é a base para o roteamento SIP (Session Initiation Protocol), que possibilita a comunicação entre computadores que executam o Servidor de Chat Persistente e a funcionalidade de Chat Persistente. 
    
- Software de en fila de mensagens. Usado pelo Servidor de Chat Persistente e serviço de Conformidade de Chat Persistente, se implantado.
    
As seções a seguir descrevem os requisitos específicos para o Servidor de Chat Persistente e o banco de dados que armazena os dados de Chat Persistente.

> [!NOTE] 
> O chat persistente está disponível no Skype for Business Server 2015, mas não é mais suportado no Skype for Business Server 2019. A mesma funcionalidade está disponível no Teams. Para saber mais, confira [Como começar a atualizar o Microsoft Teams.](/microsoftteams/upgrade-start-here) Se você precisar usar o chat persistente, suas opções são migrar os usuários que exigem essa funcionalidade para o Teams ou continuar usando o Skype for Business Server 2015. 
  
## <a name="front-end-server-requirements"></a>Requisitos do Servidor front-end

Os requisitos do Servidor front-end dependem se você está implantando o Servidor de Chat Persistente com o Skype for Business Server 2015 Enterprise Edition ou Standard Edition.
  
- Se você estiver implantando o Servidor de Chat Persistente com o Skype for Business Server 2015 Enterprise Edition, poderá implantar o Servidor front-end do Servidor de Chat Persistente em um ou mais computadores autônomos no pool Enterprise Edition. Você não pode sobressalto os Servidores front-end de Chat Persistente no Servidor front-end do Skype for Business Server 2015. 
    
    Um único Servidor Front-End de Servidor de Chat Persistente pode suportar 20.000 usuários ativos. Você pode ter um pool de Servidor de Chat Persistente com até 4 front-ends ativos, suportando um total de 80.000 usuários simultâneos. 
    
- Se você estiver implantando o Servidor de Chat Persistente com o Skype for Business Server 2015 Standard Edition, poderá colocar o Chat Persistente com o Servidor Front-End. Essa implantação de servidor único pode dar suporte a até 20.000 usuários. 
    
## <a name="persistent-chat-server-database-requirements"></a>Requisitos de banco de dados do Servidor de Chat Persistente

O Servidor de Chat Persistente requer o software de banco de dados do SQL Server para armazenar o histórico e o conteúdo da sala de chat, os dados de configuração, os dados de provisionamento do usuário e outros metadados relevantes. Opcionalmente, ele usa o banco de dados de Conformidade de Chat Persistente para armazenar dados de conformidade. Os bancos de dados de Chat Persistente podem ser alocados no mesmo SQL Server ou até mesmo na mesma instância do SQL, como os bancos de dados back-end. 
  
- Se você estiver instalando o Servidor de Chat Persistente com o Skype for Business Server 2015 Enterprise Edition, para garantir o melhor desempenho, é recomendável instalar o armazenamento de arquivos de Chat Persistente.
    
- Se você estiver instalando o Servidor de Chat Persistente com o Skype for Business Server 2015 Standard Edition, poderá implantar o Servidor #A0 do Armazenamento de Chat Persistente na instância local do SQL Server Express.
    
- O banco de dados de Chat Persistente (mgc) e o banco de dados de conformidade (mgccomp) podem estar localizados na mesma instância do SQL Server ou em diferentes SQL Servers.
    
Para preparar uma plataforma de servidor de banco de dados, certifique-se de que cada computador atenda aos requisitos de hardware e instale o software de pré-requisito. A plataforma de servidor para os servidores de banco de dados de Chat Persistente exige o mesmo hardware que o servidor de banco de dados back-end do Skype for Business Server 2015. Para obter detalhes, [consulte Requisitos de servidor para o Skype for Business Server 2015.](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
No servidor de banco de dados, certifique-se de que um dos seguintes aplicativos de software está instalado:

- Microsoft SQL Server 2017 com o service pack mais recente.

- Microsoft SQL Server 2016 com Service Pack 1 e você deve executar com a Atualização Cumulativa 7 ou posterior do Skype for Business Server. Recomendamos executar o SQL Server 2016 com o service pack mais recente. Para obter detalhes sobre como instalar o Microsoft SQL Server 2016, consulte [Instalar o SQL Server 2016.](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016)

- Microsoft SQL Server 2014, e você deve executar com a Atualização Cumulativa 6 ou posterior do Skype for Business Server. Recomendamos executar o SQL Server 2014 com o service pack mais recente. Para obter detalhes sobre como instalar o Microsoft SQL Server 2014, consulte [Instalar o SQL Server 2014.](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014)

- Microsoft SQL Server 2012 (edição de 64 bits), e recomendamos a execução com o service pack mais recente. Para obter detalhes sobre como instalar o Microsoft SQL Server 2012, consulte [Instalar o SQL Server 2012.](https://go.microsoft.com/fwlink/p/?LinkID=248559)

## <a name="persistent-chat-server-certificate-requirements"></a>Requisitos de certificado do Servidor de Chat Persistente

Para obter detalhes sobre como adquirir certificados, criar o banco de dados do SQL Server e criar armazenamentos de arquivos, consulte [Implantar o Skype for Business Server 2015.](../../deploy/deploy.md) 
  
## <a name="for-more-information"></a>Para obter mais informações

Para obter mais informações sobre os requisitos de hardware e software, consulte os seguintes tópicos:
  
- [Requisitos de servidor para o Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [Requisitos ambientais do Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

