---
title: Requisitos de hardware e software para o servidor de chat persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/19/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: 'Resumo: Leia este tópico para saber mais sobre os requisitos de hardware e software para o servidor de chat persistente no Skype for Business Server 2015.'
ms.openlocfilehash: 39204b675feff78fef56ee02e1c7e381eb36f65f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213227"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Requisitos de hardware e software para o servidor de chat persistente no Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber mais sobre os requisitos de hardware e software para o servidor de chat persistente no Skype for Business Server 2015.
  
O servidor de chat persistente pode ser instalado com o Skype for Business Server 2015 Enterprise Edition ou Standard Edition. Os requisitos dependem de qual edição do Skype for Business Server 2015 você instalou e dos requisitos de desempenho de sua empresa. Enterprise Edition pode suportar até 80.000 usuários simultâneos; A Standard Edition pode suportar até 20.000 usuários simultâneos. O chat persistente consiste em um componente front-end, bem como um componente de banco de dados SQL de back-end.
  
Antes de implantar o servidor de chat persistente, você deve garantir que os seguintes requisitos de hardware e software sejam atendidos:
  
- Hardware que atende aos requisitos mínimos para oferecer suporte ao Skype for Business Server 2015, servidor de chat persistente, servidores de banco de dados e servidores de arquivos. Para obter mais informações, consulte [Server Requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Sistema operacional e software de banco de dados suportados.
    
    Para obter detalhes sobre os sistemas operacionais e o software de banco de dados com suporte e os requisitos do Windows Update, consulte [Server Requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Servidor front-end do Skype for Business Server 2015. O servidor front-end é a base para o roteamento do protocolo SIP, que faz a comunicação entre os computadores que executam o servidor de chat persistente e a funcionalidade de chat persistente possível. 
    
- Software de enfileiramento de mensagens. Usado pelo servidor de chat persistente e pelo serviço de conformidade de chat persistente, se implantado.
    
As seções a seguir descrevem os requisitos específicos para o servidor de chat persistente e o banco de dados que armazena os dados de chat persistente.

> [!NOTE] 
> O chat persistente está disponível no Skype for Business Server 2015, mas não tem mais suporte no Skype for Business Server 2019. A mesma funcionalidade está disponível no Teams. Para obter mais informações, consulte [introdução à atualização do Microsoft Teams](/microsoftteams/upgrade-start-here). Se você precisar usar o chat persistente, suas escolhas serão migrar usuários que exijam essa funcionalidade para o Microsoft Teams ou para continuar usando o Skype for Business Server 2015. 
  
## <a name="front-end-server-requirements"></a>Requisitos do servidor front-end

Os requisitos do servidor de front-end dependem se você está implantando o servidor de chat persistente com o Skype for Business Server 2015 Enterprise Edition ou Standard Edition.
  
- Se você estiver implantando o servidor de chat persistente com o Skype for Business Server 2015 Enterprise Edition, poderá implantar o servidor front-end do servidor de chat persistente em um ou mais computadores autônomos no pool Enterprise Edition. Não é possível colocar os servidores front-end de chat persistente no servidor front-end do Skype for Business Server 2015. 
    
    Um servidor front-end único de servidor de chat persistente pode oferecer suporte A 20.000 usuários ativos. Você pode ter um pool de servidores de chat persistente com até 4 front-ends ativos, suportando um total de 80.000 usuários simultâneos. 
    
- Se você estiver implantando o servidor de chat persistente com o Skype for Business Server 2015 Standard Edition, poderá colocar o chat persistente com o servidor front-end. Esta implantação de servidor único pode suportar até 20.000 usuários. 
    
## <a name="persistent-chat-server-database-requirements"></a>Requisitos de banco de dados do servidor de chat persistente

O servidor de chat persistente requer o software de banco de dados do SQL Server para armazenar o histórico de salas de chat e o conteúdo, dados de configuração, dados de provisionamento do usuário e outros metadados relevantes. Opcionalmente, ele usa o banco de dados de conformidade de chat persistente para armazenar dados de conformidade. Os bancos de dados de chat persistente podem ser colocados no mesmo SQL Server, ou até na mesma instância SQL, como os bancos de dados de back-end. 
  
- Se você estiver instalando o servidor de chat persistente com o Skype for Business Server 2015 Enterprise Edition, para garantir o desempenho ideal, é recomendável instalar o repositório de arquivos de chat persistente.
    
- Se você estiver instalando o servidor de chat persistente com o Skype for Business Server 2015 Standard Edition, poderá implantar o servidor back-end do repositório de chat persistente na instância local do SQL Server Express.
    
- O banco de dados de chat persistente (MGC) e o banco de dados de conformidade (mgccomp) podem estar localizados na mesma instância do SQL Server ou em servidores SQL diferentes.
    
Para preparar uma plataforma de servidor de banco de dados, certifique-se de que cada computador atende aos requisitos de hardware e instale o software de pré-requisito. A plataforma de servidor para os servidores de banco de dados de chat persistente requer o mesmo hardware que o servidor de banco de dados back-end do Skype for Business Server 2015. Para obter detalhes, consulte [Server Requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
  
No servidor de banco de dados, certifique-se de que um dos seguintes aplicativos de software está instalado:

- Microsoft SQL Server 2017 com o Service Pack mais recente.

- Microsoft SQL Server 2016 com Service Pack 1 e você deve executar a atualização cumulativa 7 ou posterior do Skype for Business Server. Recomendamos a execução do SQL Server 2016 com o Service Pack mais recente. Para obter detalhes sobre como instalar o Microsoft SQL Server 2016, consulte [install SQL server 2016](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016).

- Microsoft SQL Server 2014, e você deve executar a atualização cumulativa 6 ou posterior do Skype for Business Server. Recomendamos a execução do SQL Server 2014 com o Service Pack mais recente. Para obter detalhes sobre como instalar o Microsoft SQL Server 2014, consulte [install SQL server 2014](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014).

- Microsoft SQL Server 2012 (64-bit Edition) e recomendamos a execução com o Service Pack mais recente. Para obter detalhes sobre como instalar o Microsoft SQL Server 2012, consulte [install SQL server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559).

## <a name="persistent-chat-server-certificate-requirements"></a>Requisitos de certificado do servidor de chat persistente

Para obter detalhes sobre a aquisição de certificados, criação do banco de dados do SQL Server e criação de repositórios de arquivos, consulte [Deploy Skype for Business server 2015](../../deploy/deploy.md). 
  
## <a name="for-more-information"></a>Para obter mais informações

Para obter mais informações sobre requisitos de hardware e software, consulte os seguintes tópicos:
  
- [Requisitos de servidor para o Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [Requisitos ambientais para o Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

