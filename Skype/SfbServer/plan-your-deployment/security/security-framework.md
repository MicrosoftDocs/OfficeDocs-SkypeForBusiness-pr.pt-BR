---
title: Estrutura de segurança do Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: Esta seção fornece uma visão geral dos elementos fundamentais que formam a estrutura de segurança do Skype para Business Server. Noções básicas sobre como esses elementos funcionam em conjunto é essencial para tomar decisões fundamentadas sobre como proteger sua Skype específica para implantação de servidor de negócios.
ms.openlocfilehash: 7c678e1f005178b569f8e4136d40fd911483a3d5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879879"
---
# <a name="security-framework-for-skype-for-business-server"></a>Estrutura de segurança do Skype para Business Server
 
Esta seção fornece uma visão geral dos elementos fundamentais que formam a estrutura de segurança do Skype para Business Server. Noções básicas sobre como esses elementos funcionam em conjunto é essencial para tomar decisões fundamentadas sobre como proteger sua Skype específica para implantação de servidor de negócios.
  
Esses elementos são:
  
- Serviços de domínio Active Directory (AD DS) fornece um repositório back-end confiável para contas de usuário e recursos de rede.
    
- O controle de acesso baseado em função (RBAC) permite delegar tarefas administrativas enquanto mantém altos padrões de segurança.
    
- A infraestrutura de chave pública (PKI) utiliza certificados emitidos por autoridades de certificação (CAs) confiáveis para autenticar servidores e garantir a integridade de dados.
    
- A segurança da camada de transporte (TLS), HTTPS sobre SSL (HTTPS) e TLS mútuo (MTLS) possibilitam a autenticação de ponto de extremidade e criptografia IM. Os fluxos de áudio e vídeo ponto a ponto e de compartilhamento de aplicativos são criptografados utilizando protocolo de transporte em tempo real seguro (SRTP).
    
- Protocolos padrão do setor para autenticação do usuário, onde possível.
    
- Windows PowerShell fornece recursos de segurança que estão habilitados por padrão, de modo que os usuários não podem facilmente ou inconscientemente executar scripts.
    
Esses elementos de segurança fundamentais funcionam juntos para definir usuários confiáveis, servidores, conexões e operações para ajudar a garantir uma base segura para Skype para Business Server.
  
## <a name="in-this-section"></a>Nesta seção

Os tópicos desta seção descrevem como cada um desses elementos fundamentais aprimoram a segurança da sua Skype infra-estrutura de servidor de negócios.
  
- [Serviços de domínio do Active Directory para Skype para Business Server](active-directory-domain-services.md)
    
- [Controle de acesso baseado em função (RBAC) para Skype para Business Server](role-based-access-control-rbac.md)
    
- [Infraestrutura de chave pública para Skype para Business Server](public-key-infrastructure-for-skype.md)
    
- [TLS e MTLS para Skype para Business Server](tls-and-mtls.md)
    
- [Criptografia do Skype para Business Server](encryption.md)
    
- [Autenticação de cliente e usuário para Skype para Business Server](user-and-client-authentication.md)
    
- [Windows PowerShell e Skype para as ferramentas de gerenciamento de servidor de negócios](management-tools.md)
    

