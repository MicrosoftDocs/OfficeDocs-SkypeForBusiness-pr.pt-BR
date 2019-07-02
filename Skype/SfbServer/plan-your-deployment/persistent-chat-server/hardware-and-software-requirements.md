---
title: Requisitos de hardware e software para Servidor de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/19/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: 'Resumo: Leia este tópico para saber mais sobre os requisitos de hardware e software para o servidor de chat persistente no Skype for Business Server 2015.'
ms.openlocfilehash: e700b76c8af29a0c877c1dc594244a299b8a3904
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418442"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Requisitos de hardware e software para Servidor de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber mais sobre os requisitos de hardware e software para o servidor de chat persistente no Skype for Business Server 2015.
  
O servidor de chat persistente pode ser instalado com o Skype for Business Server 2015 Enterprise Edition ou Standard Edition. Os requisitos dependem de qual edição do Skype for Business Server 2015 você instalou e dos requisitos de desempenho de sua empresa. A Enterprise Edition aceita até 80.000 usuários concomitantes; a Standard Edition aceita até 20.000 usuários concomitantes. O Chat Persistente consiste em um componente front-end e em um componente de banco de dados SQL back-end.
  
Antes de implantar o servidor de chat persistente, você deve certificar-se de que os seguintes requisitos de hardware e software sejam atendidos:
  
- Hardware que atende aos requisitos mínimos para dar suporte ao Skype for Business Server 2015, servidor de chat persistente, servidores de banco de dados e servidores de arquivos. Para obter mais informações, consulte [requisitos do servidor para o Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Sistema operacional e software de banco de dados suportados.
    
    Para obter detalhes sobre sistemas operacionais com suporte e software de banco de dados e requisitos do Windows Update, consulte [requisitos do servidor para o Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Servidor front-end do Skype for Business Server 2015. O servidor front-end é a base para o roteamento SIP (Session Initiation Protocol), que faz a comunicação entre computadores que executam o servidor de chat persistente e a funcionalidade de chat persistente possível. 
    
- Software de Enfileiramento de Mensagens. Usado pelo servidor de chat persistente e pelo serviço de conformidade de chat persistente, se implantado.
    
As seções a seguir descrevem os requisitos específicos para o servidor de chat persistente e o banco de dados que armazena os dados de chat persistente.

> [!NOTE] 
> O chat persistente está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019. A mesma funcionalidade está disponível no Microsoft Teams. Para obter mais informações, consulte [introdução à atualização do Microsoft Teams](/microsoftteams/upgrade-start-here). Se você precisar usar chats persistentes, suas opções serão migrar os usuários que exigem essa funcionalidade para o Microsoft Teams ou para continuar usando o Skype for Business Server 2015. 
  
## <a name="front-end-server-requirements"></a>Requisitos do Servidor Front-End

Os requisitos de servidor front-end dependem se você está implantando o servidor de chat persistente com o Skype for Business Server 2015 Enterprise Edition ou Standard Edition.
  
- Se você estiver implantando um servidor de chat persistente com o Skype for Business Server 2015 Enterprise Edition, poderá implantar o servidor front-end do servidor de chat persistente em um ou mais computadores autônomos no pool da Enterprise Edition. Você não pode colocar os servidores de front-end de chat persistente no servidor front-end do Skype for Business Server 2015. 
    
    Um servidor front-end único de servidor de chat persistente pode oferecer suporte a usuários ativos do 20.000. Você pode ter um pool de servidores de chat persistente com até 4 front-ends ativos, oferecendo suporte a um total de 80.000 usuários simultâneos. 
    
- Se você estiver implantando um servidor de chat persistente com o Skype for Business Server 2015 Standard Edition, poderá posicionar o chat persistente com o servidor front-end. Essa implantação de servidor único aceita até 20.000 usuários. 
    
## <a name="persistent-chat-server-database-requirements"></a>Requisitos de banco de dados persistente do servidor de chat

O servidor de chat persistente requer o software de banco de dados do SQL Server para armazenar o conteúdo e o conteúdo da sala de chat, dados de configuração, dados de provisionamento do usuário e outros metadados relevantes. Opcionalmente, ele usa o banco de dados de conformidade de chat persistente para armazenar dados de conformidade. Os bancos de dados de Chat Persistente podem ser colocados no mesmo SQL Server, ou até na mesma instância do SQL, como os bancos de dados back-end. 
  
- Se você estiver instalando o servidor de chat persistente com o Skype for Business Server 2015 Enterprise Edition, para garantir o desempenho ideal, é recomendável que você instale o repositório de arquivos de chat persistente.
    
- Se você estiver instalando o servidor de chat persistente com o Skype for Business Server 2015 Standard Edition, poderá implantar o servidor back-end do repositório de chat persistente na instância local do SQL Server Express.
    
- O banco de dados de chat persistente (MGC) e o banco de dados de conformidade (mgccomp) podem estar localizados na mesma instância do SQL Server ou em servidores SQL diferentes.
    
Para preparar uma plataforma de servidor de banco de dados, verifique se todos os computadores atendem aos requisitos de hardware, depois instale o software de pré-requisito. A plataforma do servidor para os servidores de banco de dados de chat persistente requer o mesmo hardware que o servidor de banco de dados back-end do Skype for Business Server 2015. Para obter mais detalhes, consulte [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
  
No servidor de banco de dados. verifique se um dos seguintes aplicativos de software está instalado:

- Microsoft SQL Server 2017 com o Service Pack mais recente.

- Microsoft SQL Server 2016 com Service Pack 1, e você deve executar com a atualização cumulativa 7 do Skype for Business Server ou versões posteriores. Recomendamos a execução do SQL Server 2016 com o Service Pack mais recente. Para obter detalhes sobre como instalar o Microsoft SQL Server 2016, consulte [instalar o SQL server 2016](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016).

- Microsoft SQL Server 2014, e você deve executar com a atualização cumulativa 6 ou versões posteriores do Skype for Business Server. Recomendamos a execução do SQL Server 2014 com o Service Pack mais recente. Para obter detalhes sobre como instalar o Microsoft SQL Server 2014, consulte [instalar o SQL server 2014](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014).

- Microsoft SQL Server 2012 (64-bit Edition) e recomendamos a execução com o Service Pack mais recente. Para obter detalhes sobre como instalar o Microsoft SQL Server 2012, consulte [instalar o SQL server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559).

## <a name="persistent-chat-server-certificate-requirements"></a>Requisitos de certificado do servidor de chat persistente

Para obter detalhes sobre como adquirir certificados, criar o banco de dados do SQL Server e criar armazenamentos de arquivos, consulte [implantar o Skype for Business Server 2015](../../deploy/deploy.md). 
  
## <a name="for-more-information"></a>Para obter mais informações

Para obter informações sobre os requisitos de hardware e software, consulte os seguintes tópicos:
  
- [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

