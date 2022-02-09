---
title: Planejamento para autenticação moderna (ADAL) com Skype for Business
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: Este artigo explica o que é a Autenticação Moderna (baseada na Biblioteca de Autenticação do Active Directory (ADAL) e OAuth 2.0.
ms.openlocfilehash: ca029b4a1f93f5e498df902587bb754247193ab4
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62404593"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Como usar a Autenticação Moderna (ADAL) com Skype for Business
 
Este artigo apresenta a Autenticação Moderna (baseada na Biblioteca de Autenticação do Active Directory (ADAL) e no OAuth 2.0, que podem ser encontradas na Atualização Cumulativa de março de 2016 do Skype for Business para Skype for Business Server 2015 ou na versão inicial do Skype for Business Server 2019.
  
## <a name="what-is-adal"></a>O que é a ADAL?

ADAL é o acrônimo para a 'Biblioteca de Autenticação do Active Directory', e, juntamente com o OAuth 2.0, é um subsúldo da Autenticação Moderna. Essa biblioteca de códigos foi projetada para disponibilizar recursos protegidos em seu diretório para aplicativos cliente (como Skype for Business) por meio de tokens de segurança. O ADAL funciona com o OAuth 2.0 para habilitar mais cenários de autenticação e autorização, como a Autenticação Multifatória (MFA) e mais formas de SAML Auth.
  
Uma variedade de aplicativos que atuam como clientes pode aproveitar a Autenticação Moderna para obter ajuda para obter recursos protegidos. Em Skype for Business Server, essa tecnologia é usada entre clientes locais e servidores locais para dar aos usuários um nível adequado de autorização para os recursos.
  
As conversas de Autenticação Moderna (baseadas no ADAL e no OAuth 2.0) têm alguns elementos em comum.
  
- Há um cliente fazendo uma solicitação para um recurso, nesse caso, o cliente é Skype for Business.
    
- Há um recurso para o qual o cliente precisa de um nível específico de acesso, e esse recurso é protegido por um serviço de diretório, nesse caso, o recurso é Skype for Business Server.
    
- Há uma conexão OAuth, em outras palavras, uma conexão  *dedicada à*  autorização de um usuário para acessar um recurso. (OAuth também é conhecido pelo nome mais descritivo, 'Server-to-Server' auth, e geralmente é abreviado como S2S.)
    
Em Skype for Business Server de Autenticação Moderna (ADAL), o Skype for Business Server se comunica por meio do ADFS (ADFS 3.0 no Windows Server 2012 R2). A autenticação pode acontecer usando algum outro Provedor de Identidade (IdP), mas Skype for Business servidor precisa ser configurado para se comunicar diretamente com o ADFS. Se você não configurou o ADFS para trabalhar com Skype for Business Server, conclua [a instalação do ADFS](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10)).
  
O ADAL está incluído na Atualização Cumulativa de março de 2016 para o Skype for Business Server 2015, e a Atualização Cumulativa de março de 2016 para Skype for Business deve ser instalada e  é necessária para uma configuração bem-sucedida. Para Skype for Business Server 2019, ele está disponível na versão inicial do produto.
  
> [!NOTE]
> Durante a versão inicial, a Autenticação Moderna em um ambiente local só é suportada se não houver uma topologia Skype misturada envolvida. Por exemplo, se o ambiente for puramente Skype for Business Server. Essa instrução pode estar sujeita a alterações. 
  
Um pacote do PowerShell incluindo .ps1 arquivos com os comandos usados pelo ADAL deve ser baixado para uma configuração bem-sucedida.

Para obter informações sobre como implementar a Autenticação Moderna no Skype for Business, consulte: How [to use Modern Authentication (ADAL) with Skype for Business](/microsoft-365/enterprise/hybrid-modern-auth-overview)