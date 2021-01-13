---
title: Estrutura de segurança do Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: Esta seção fornece uma visão geral dos elementos fundamentais que formam a estrutura de segurança do Skype for Business Server. Entender como esses elementos funcionam em conjunto é essencial para tomar decisões informadas sobre como proteger sua implantação específica do Skype for Business Server.
ms.openlocfilehash: 94d2ffac30e029ab6631557a69d6da3ec108657f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832091"
---
# <a name="security-framework-for-skype-for-business-server"></a>Estrutura de segurança do Skype for Business Server
 
Esta seção fornece uma visão geral dos elementos fundamentais que formam a estrutura de segurança do Skype for Business Server. Entender como esses elementos funcionam em conjunto é essencial para tomar decisões informadas sobre como proteger sua implantação específica do Skype for Business Server.
  
Essas elementos são os seguintes:
  
- O AD DS (Serviços de Domínio Active Directory) fornece um repositório back-end confiável para contas de usuário e recursos de rede.
    
- Role-Based Controle de Acesso (RBAC) permite delegar tarefas administrativas enquanto mantém altos padrões de segurança.
    
- A PKI (Infraestrutura de Chave Pública) usa certificados emitidos por autoridades de certificação confiáveis (CAs) para autenticar servidores e garantir a integridade dos dados.
    
- Os protocolos TLS, HTTP sobre SSL (HTTPS) e MTLS (TLS mútuo) permitem a autenticação de ponto de extremidade e a criptografia de mensagens instantâneas. Os fluxos de compartilhamento ponto a ponto de áudio, vídeo e aplicativo são criptografados usando SRTP (Secure Real-Time Transport Protocol).
    
- Protocolos padrão do setor para autenticação do usuário, quando possível.
    
- O Windows PowerShell fornece recursos de segurança habilitados por padrão, de modo que os usuários não possam executar scripts com facilidade ou sem saber.
    
Esses elementos de segurança fundamentais trabalham juntos para definir usuários, servidores, conexões e operações confiáveis para ajudar a garantir uma base segura para o Skype for Business Server.
  
## <a name="in-this-section"></a>Nesta seção

Os tópicos desta seção descrevem como cada um desses elementos fundamentais funciona para melhorar a segurança da infraestrutura do Skype for Business Server.
  
- [Serviços de Domínio do Active Directory para Skype for Business Server](active-directory-domain-services.md)
    
- [Controle de acesso baseado em função (RBAC) para Skype for Business Server](role-based-access-control-rbac.md)
    
- [Infraestrutura de chave pública para o Skype for Business Server](public-key-infrastructure-for-skype.md)
    
- [TLS e MTLS para Skype for Business Server](tls-and-mtls.md)
    
- [Criptografia para o Skype for Business Server](encryption.md)
    
- [Autenticação de usuário e cliente para o Skype for Business Server](user-and-client-authentication.md)
    
- [Ferramentas de gerenciamento do Windows PowerShell e do Skype for Business Server](management-tools.md)
    

