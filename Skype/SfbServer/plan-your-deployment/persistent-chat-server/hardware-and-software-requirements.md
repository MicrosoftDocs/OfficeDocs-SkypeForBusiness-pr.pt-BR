---
title: Requisitos de hardware e software para Servidor de Chat Persistente no Skype for Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/19/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: 'Resumo: Leia este tópico para saber mais sobre os requisitos de hardware e software para o servidor de Chat persistente no Skype para Business Server 2015.'
ms.openlocfilehash: 16a04616a1ec15b4cfffc17cd3a3d9bc271b0dde
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21027000"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Requisitos de hardware e software para Servidor de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber mais sobre os requisitos de hardware e software para o servidor de Chat persistente no Skype para Business Server 2015.
  
Servidor de Chat persistente pode ser instalado com Skype para Business Server 2015 Enterprise Edition ou Standard Edition. Requisitos dependem de qual edição do Skype para Business Server 2015 que você instalou e as exigências de desempenho do seu negócio. A Enterprise Edition aceita até 80.000 usuários concomitantes; a Standard Edition aceita até 20.000 usuários concomitantes. O Chat Persistente consiste em um componente front-end e em um componente de banco de dados SQL back-end.
  
Antes de implantar o servidor de Chat persistente, você deve garantir que os seguintes requisitos de hardware e software sejam atendidos:
  
- Hardware que atende os requisitos mínimos para suportar Skype para Business Server 2015, servidor de Chat persistente, os servidores de banco de dados e servidores de arquivo. Para obter mais informações, consulte [requisitos de servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Sistema operacional e software de banco de dados suportados.
    
    Para obter detalhes sobre o software de banco de dados e sistemas operacionais suportados e Windows atualização requisitos, consulte [requisitos de servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Skype para o servidor de Front-End Server 2015 corporativos. Servidor Front-End é a base para Session Initiation Protocol (SIP) roteamento, que torna possível a comunicação entre os computadores que executam o servidor de Chat persistente e a funcionalidade de Chat persistente. 
    
- Software de Enfileiramento de Mensagens. Usado pelo serviço servidor de Chat persistente e conformidade de Chat persistente, se implantado.
    
As seções a seguir descrevem os requisitos específicos para o servidor de Chat persistente e o banco de dados que armazena os dados de Chat persistente.

> [!NOTE] 
> Bate-papo persistente está disponível no Skype para Business Server 2015, mas não é mais suportado no Skype para Business Server 2019. A mesma funcionalidade está disponível em equipes. Para obter mais informações, consulte [jornada do Skype para negócios às equipes da Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Se você precisar utilizar o chat persistente, suas opções são para migrar tanto os usuários que requerem essa funcionalidade para equipes ou para continuar usando o Skype para Business Server 2015. 
  
## <a name="front-end-server-requirements"></a>Requisitos do Servidor Front-End

Requisitos de Front End Server dependem se você estiver implantando o servidor de Chat persistente com Skype para Business Server 2015 Enterprise Edition ou Standard Edition.
  
- Se você estiver implantando o servidor de Chat persistente com Skype para Business Server 2015 Enterprise Edition, você poderá implantar Persistent Chat Server servidor Front-End em um ou mais computadores autônomos do pool Enterprise Edition. Você não pode ser colocada Persistent Chat servidores Front-End no Skype para Business Server 2015 servidor Front-End. 
    
    Um único Persistent Chat Server servidor Front-End pode oferecer suporte a 20.000 usuários ativos. Você pode ter um pool do servidor de Chat persistente com até 4 ativos front-ends, portanto, suportando um total de 80.000 usuários simultâneos. 
    
- Se você estiver implantando o servidor de Chat persistente com Skype para Business Server 2015 Standard Edition, você pode colocar o Chat persistente com o servidor Front-End. Essa implantação de servidor único aceita até 20.000 usuários. 
    
## <a name="persistent-chat-server-database-requirements"></a>Requisitos de banco de dados de servidor de Chat persistentes

Persistent Chat Server requer o software de banco de dados do SQL Server para armazenar o histórico de sala de chat e conteúdo, dados de configuração, dados de provisionamento de usuário e outros metadados relevantes. Opcionalmente, ele usa o banco de dados de conformidade de Chat persistente para armazenar dados de conformidade. Os bancos de dados de Chat Persistente podem ser colocados no mesmo SQL Server, ou até na mesma instância do SQL, como os bancos de dados back-end. 
  
- Se você estiver instalando o servidor de Chat persistente com Skype para Business Server 2015 Enterprise Edition, para garantir o desempenho ideal, é recomendável que você instale o repositório de arquivos de Chat persistente.
    
- Se você estiver instalando o servidor de Chat persistente com Skype para 2015 Business Server Standard edition, você poderá implantar a Persistent Chat repositório servidor Back-End na instância do SQL Server Express local.
    
- O banco de dados de bate-papo persistente (mgc) e o banco de dados de conformidade (mgccomp) podem estar localizados na mesma instância do SQL Server ou em servidores diferentes do SQL.
    
Para preparar uma plataforma de servidor de banco de dados, verifique se todos os computadores atendem aos requisitos de hardware, depois instale o software de pré-requisito. A plataforma de servidor para os servidores de banco de dados de Chat persistente requer os mesmos itens de hardware do Skype para servidor de banco de dados de back-end do Business Server 2015. Para obter detalhes, consulte [requisitos de servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
  
No servidor de banco de dados. verifique se um dos seguintes aplicativos de software está instalado:

- Microsoft SQL Server 2014 e você deve executar com Skype para 6 de atualização cumulativa do Business Server ou versões posteriores. É recomendável que executa o SQL Server 2014 com o service pack mais recente. Para obter detalhes sobre como instalar o Microsoft SQL Server 2014, consulte [instalar o SQL Server 2014](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014).

- Microsoft SQL Server 2012 (edição de 64 bits) e é recomendável execução com o service pack mais recente. Para obter detalhes sobre como instalar o Microsoft SQL Server 2012, consulte [instalar o SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559).

- Microsoft SQL Server 2008 R2 (64-bit edition) e é recomendado para execução com o service pack mais recente. Para obter detalhes sobre como instalar o Microsoft SQL Server 2008 R2, consulte [Instalação do SQL Server (SQL Server 2008 R2)](https://go.microsoft.com/fwlink/p/?LinkId=275702). 
    
## <a name="persistent-chat-server-certificate-requirements"></a>Requisitos de certificado de servidor de Chat persistentes

Para obter detalhes sobre a aquisição de certificados, criando o banco de dados do SQL Server e criando repositórios de arquivos, consulte [Implantar Skype para Business Server 2015](../../deploy/deploy.md). 
  
## <a name="for-more-information"></a>Para obter mais informações

Para obter informações sobre os requisitos de hardware e software, consulte os seguintes tópicos:
  
- [Requisitos de servidor no Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [Requisitos de ambiente para o Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

