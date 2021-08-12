---
title: Estrutura de segurança para Skype for Business Server
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
description: Esta seção fornece uma visão geral dos elementos fundamentais que formam a estrutura de segurança para Skype for Business Server. Entender como esses elementos funcionam em conjunto é essencial para tomar decisões informadas sobre como proteger sua implantação Skype for Business Server específica.
ms.openlocfilehash: a0f6513f86d7416f546c6a744fc1b40df7c7137a18dae5d76fcf18166a4f2eb1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337709"
---
# <a name="security-framework-for-skype-for-business-server"></a>Estrutura de segurança para Skype for Business Server
 
Esta seção fornece uma visão geral dos elementos fundamentais que formam a estrutura de segurança para Skype for Business Server. Entender como esses elementos funcionam em conjunto é essencial para tomar decisões informadas sobre como proteger sua implantação Skype for Business Server específica.
  
Essas elementos são os seguintes:
  
- O AD DS (Serviços de Domínio Active Directory) fornece um repositório back-end confiável para contas de usuário e recursos de rede.
    
- Role-Based Controle de Acesso (RBAC) permite delegar tarefas administrativas enquanto mantém altos padrões de segurança.
    
- A Infraestrutura de Chave Pública (PKI) usa certificados emitidos por autoridades de certificação confiáveis (CAs) para autenticar servidores e garantir a integridade dos dados.
    
- Os protocolos TLS, HTTP sobre SSL (HTTPS) e MTLS (TLS mútuo) permitem a autenticação de ponto de extremidade e a criptografia de mensagens instantâneas. Os fluxos de compartilhamento ponto a ponto de áudio, vídeo e aplicativo são criptografados usando SRTP (Secure Real-Time Transport Protocol).
    
- Protocolos padrão do setor para autenticação do usuário, quando possível.
    
- O Windows PowerShell fornece recursos de segurança habilitados por padrão, de modo que os usuários não possam executar scripts com facilidade ou sem saber.
    
Esses elementos de segurança fundamentais trabalham em conjunto para definir usuários confiáveis, servidores, conexões e operações para ajudar a garantir uma base segura para Skype for Business Server.
  
## <a name="in-this-section"></a>Nesta seção

Os tópicos nesta seção descrevem como cada um desses elementos fundamentais funciona para melhorar a segurança de sua Skype for Business Server infraestrutura.
  
- [Serviços de Domínio do Active Directory para Skype for Business Server](active-directory-domain-services.md)
    
- [Controle de acesso baseado em função (RBAC) para Skype for Business Server](role-based-access-control-rbac.md)
    
- [Infraestrutura de chave pública para Skype for Business Server](public-key-infrastructure-for-skype.md)
    
- [TLS e MTLS para Skype for Business Server](tls-and-mtls.md)
    
- [Criptografia para Skype for Business Server](encryption.md)
    
- [Autenticação de usuário e cliente para Skype for Business Server](user-and-client-authentication.md)
    
- [Windows PowerShell e ferramentas Skype for Business Server de gerenciamento](management-tools.md)
    

