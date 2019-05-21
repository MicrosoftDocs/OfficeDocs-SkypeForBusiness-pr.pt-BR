---
title: Estrutura de segurança do Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: Esta seção fornece uma visão geral dos elementos fundamentais que formam a estrutura de segurança do Skype for Business Server. Entender como esses elementos funcionam juntos é essencial para tomar decisões conscientes sobre como proteger sua implantação específica do Skype for Business Server.
ms.openlocfilehash: 8b82b09a8220139abe62ac4503ad8a7eddc28e99
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296872"
---
# <a name="security-framework-for-skype-for-business-server"></a>Estrutura de segurança do Skype for Business Server
 
Esta seção fornece uma visão geral dos elementos fundamentais que formam a estrutura de segurança do Skype for Business Server. Entender como esses elementos funcionam juntos é essencial para tomar decisões conscientes sobre como proteger sua implantação específica do Skype for Business Server.
  
Esses elementos são:
  
- O AD DS (serviços de domínio Active Directory) fornece um único repositório de back-end confiável para contas de usuário e recursos de rede.
    
- O controle de acesso baseado em função (RBAC) permite delegar tarefas administrativas enquanto mantém altos padrões de segurança.
    
- A infraestrutura de chave pública (PKI) utiliza certificados emitidos por autoridades de certificação (CAs) confiáveis para autenticar servidores e garantir a integridade de dados.
    
- A segurança da camada de transporte (TLS), HTTPS sobre SSL (HTTPS) e TLS mútuo (MTLS) possibilitam a autenticação de ponto de extremidade e criptografia IM. Os fluxos de áudio e vídeo ponto a ponto e de compartilhamento de aplicativos são criptografados utilizando protocolo de transporte em tempo real seguro (SRTP).
    
- Protocolos padrão do setor para autenticação do usuário, onde possível.
    
- O Windows PowerShell fornece recursos de segurança habilitados por padrão para que os usuários não possam executar scripts de forma fácil ou desconhecida.
    
Esses elementos de segurança fundamentais trabalham juntos para definir usuários, servidores, conexões e operações confiáveis para ajudar a garantir uma base segura para o Skype for Business Server.
  
## <a name="in-this-section"></a>Nesta seção

Os tópicos desta seção descrevem como cada um desses elementos fundamentais funciona para melhorar a segurança da infraestrutura do Skype for Business Server.
  
- [Serviços de domínio do Active Directory para o Skype for Business Server](active-directory-domain-services.md)
    
- [Controle de acesso baseado em função (RBAC) para o Skype for Business Server](role-based-access-control-rbac.md)
    
- [Infraestrutura de chave pública para o Skype for Business Server](public-key-infrastructure-for-skype.md)
    
- [TLS e MTLS para o Skype for Business Server](tls-and-mtls.md)
    
- [Criptografia para o Skype for Business Server](encryption.md)
    
- [Autenticação de usuário e de cliente para o Skype for Business Server](user-and-client-authentication.md)
    
- [Ferramentas de gerenciamento do Windows PowerShell e do Skype for Business Server](management-tools.md)
    

