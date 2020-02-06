---
title: Planejando a autenticação moderna (ADAL) com o Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: Este artigo explica o que é uma autenticação moderna (que é baseada na biblioteca de autenticação do Active Directory (ADAL) e no OAuth 2,0).
ms.openlocfilehash: 239dd6a49ecbec043a661e622a66eb5cb4665e96
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815829"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>How to use Modern Authentication (ADAL) with Skype for Business
 
Este artigo apresenta autenticação moderna (que é baseada na biblioteca de autenticação do Active Directory (ADAL) e no OAuth 2,0) que pode ser encontrada na atualização cumulativa 2016 de março do Skype for Business para Skype for Business Server 2015 ou em inicial lançamento do Skype for Business Server 2019.
  
## <a name="what-is-adal"></a>O que é ADAL?

ADAL é o acrônimo de “Biblioteca de Autenticação do Active Directory" e, junto com o OAuth 2.0, constitui a base da Autenticação Moderna. Esta biblioteca de código foi projetada para disponibilizar recursos protegidos em seu diretório para aplicativos cliente (como o Skype for Business) através de tokens de segurança. A ADAL interage com o OAuth 2.0 para habilitar mais cenários de autenticação e autorização, como MFA (Multi-factor Authentication), bem como mais formas de Autenticação de SAML.
  
Vários aplicativos que atuam como clientes podem aproveitar a Autenticação Moderna para obter recursos seguros. No Skype for Business Server, essa tecnologia é usada entre clientes locais e servidores locais para dar aos usuários um nível adequado de autorização aos recursos.
  
As conversas de Autenticação Moderna (que se baseiam em ADAL e OAuth 2.0) têm alguns elementos em comum.
  
- Há um cliente que faz uma solicitação para um recurso, nesse caso, o cliente é o Skype for Business.
    
- Há um recurso para o qual o cliente precisa de um nível de acesso específico e esse recurso é protegido por um serviço de diretório, nesse caso, o recurso é o Skype for Business Server.
    
- Há uma conexão OAuth, em outras palavras, uma conexão dedicada à *autorização* de um usuário para acessar um recurso. (OAuth também é conhecido pelo nome mais descritivo, autenticação "Servidor a Servidor' e é frequentemente abreviado como S2S.)
    
Nas conversas de autenticação moderna do Skype for Business Server, o Skype for Business Server se comunica pelo ADFS (ADFS 3,0 no Windows Server 2012 R2). A autenticação pode ser feita usando-se algum outro IdP (Provedor de Identidade), mas o Skype for Business Server precisa ser configurado para se comunicar com o ADFS diretamente. Se você ainda não configurou o ADFS para funcionar com o Skype for Business Server, complete a [instalação do ADFS](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).
  
O ADAL está incluído na atualização cumulativa de março de 2016 para o Skype for Business Server 2015, e a atualização cumulativa de março de 2016 para o Skype for Business **precisa** estar instalada e ser necessária para uma configuração bem-sucedida. Para o Skype for Business Server 2019, ele está disponível na versão inicial do produto.
  
> [!NOTE]
> Durante a versão inicial, a autenticação moderna em um ambiente local só tem suporte se não houver uma topologia mista do Skype envolvida. Por exemplo, se o ambiente for simplesmente o Skype for Business Server. Esta instrução pode estar sujeita a alterações. 
  
Um pacote do PowerShell incluindo arquivos .ps1 com os comandos usados por ADAL deve ser baixado para a configuração com êxito.

Para obter informações sobre como implementar a autenticação moderna no Skype for Business, consulte: [como usar a autenticação moderna (Adal) com o Skype for Business](../../manage/authentication/use-adal.md)
