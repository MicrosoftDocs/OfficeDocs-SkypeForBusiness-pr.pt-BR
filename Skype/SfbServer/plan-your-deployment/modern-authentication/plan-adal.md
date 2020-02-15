---
title: Planejamento de autenticação moderna (ADAL) com o Skype for Business
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
description: Este artigo explica o que a autenticação moderna (que se baseia na biblioteca de autenticação do Active Directory (ADAL) e no OAuth 2,0) é.
ms.openlocfilehash: 5a51b0712f33cbafc64f87f56b4d12649bfad97e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046284"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Como usar a ADAL (autenticação moderna) com o Skype for Business
 
Este artigo introduz a autenticação moderna (que se baseia na biblioteca de autenticação do Active Directory (ADAL) e no OAuth 2,0) que pode ser encontrada na atualização cumulativa 2016 de março para o Skype for Business para o Skype for Business Server 2015 ou do início lançamento do Skype for Business Server 2019.
  
## <a name="what-is-adal"></a>O que é ADAL?

A ADAL é o acrônimo para a "biblioteca de autenticação do Active Directory" e, juntamente com o OAuth 2,0, é uma base da autenticação moderna. Essa biblioteca de códigos foi projetada para tornar os recursos protegidos no seu diretório disponíveis para aplicativos clientes (como o Skype for Business) por tokens de segurança. A ADAL funciona com o OAuth 2,0 para habilitar mais cenários de autenticação e autorização, como a autenticação multifator (MFA) e mais formas de autenticação SAML.
  
Uma variedade de aplicativos que atuam como clientes podem aproveitar a autenticação moderna para ajudar a obter recursos protegidos. No Skype for Business Server, essa tecnologia é usada entre clientes locais e servidores locais para fornecer aos usuários um nível adequado de autorização para recursos.
  
As conversas de autenticação modernas (que se baseiam em ADAL e OAuth 2,0) têm alguns elementos em comum.
  
- Há um cliente fazendo uma solicitação para um recurso, neste caso, o cliente é o Skype for Business.
    
- Há um recurso para o qual o cliente precisa de um nível de acesso específico e este recurso é protegido por um serviço de diretório, nesse caso, o recurso é o Skype for Business Server.
    
- Há uma conexão OAuth, em outras palavras, uma conexão dedicada à *autorização* de um usuário para acessar um recurso. (O OAuth também é conhecido pelo nome mais descritivo, autenticação "servidor-para-servidor" e geralmente é abreviado como S2S.)
    
Nas conversas da ADAL (autenticação moderna) do Skype for Business Server, o Skype for Business Server se comunica através do ADFS (ADFS 3,0 no Windows Server 2012 R2). A autenticação pode acontecer usando outro IdP (provedor de identidade), mas o Skype for Business Server precisa ser configurado para se comunicar com o ADFS diretamente. Se você não configurou o ADFS para trabalhar com o Skype for Business Server, conclua a [instalação do ADFS](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).
  
A ADAL está incluída na atualização cumulativa de março de 2016 para o Skype for Business Server 2015, e a atualização cumulativa de março de 2016 para o Skype for Business **deve** estar instalada e ser necessária para uma configuração bem-sucedida. Para o Skype for Business Server 2019, ele está disponível na versão inicial do produto.
  
> [!NOTE]
> Durante a versão inicial, a autenticação moderna em um ambiente local só terá suporte se não houver topologia mista do Skype envolvida. Por exemplo, se o ambiente for apenas Skype for Business Server. Esta instrução pode estar sujeita a alterações. 
  
Um pacote do PowerShell incluindo arquivos. ps1 com os comandos usados pela ADAL deve ser baixado para uma configuração bem-sucedida.

Para obter informações sobre como implementar a autenticação moderna no Skype for Business, consulte: [como usar a autenticação moderna (Adal) com o Skype for Business](../../manage/authentication/use-adal.md)
