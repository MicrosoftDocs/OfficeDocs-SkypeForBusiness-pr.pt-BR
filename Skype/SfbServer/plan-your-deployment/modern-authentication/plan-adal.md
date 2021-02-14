---
title: Planejamento da Autenticação Moderna (ADAL) com o Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: Este artigo explica o que é a Autenticação Moderna (baseada na ADAL (Biblioteca de Autenticação do Active Directory) e no OAuth 2.0.
ms.openlocfilehash: bd5d172fe4589cbd28c5b22507ad8603695ed62f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816221"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Como usar a Autenticação Moderna (ADAL) com o Skype for Business
 
Este artigo apresenta a Autenticação Moderna (que se baseia na ADAL (Biblioteca de Autenticação do Active Directory) e no OAuth 2.0) que pode ser encontrada na Atualização Cumulativa de março de 2016 do Skype for Business para Skype for Business Server 2015 ou na versão inicial do Skype for Business Server 2019.
  
## <a name="what-is-adal"></a>O que é a ADAL?

A ADAL é o acrônimo para a "Biblioteca de Autenticação do Active Directory" e, juntamente com o OAuth 2.0, é um dos princípios da Autenticação Moderna. Essa biblioteca de códigos foi projetada para disponibilizar recursos seguros em seu diretório para aplicativos cliente (como o Skype for Business) por meio de tokens de segurança. A ADAL trabalha com o OAuth 2.0 para habilitar mais cenários de autenticação e autorização, como a MFA (Autenticação Multifatória) e mais formas de Autenticação SAML.
  
Uma variedade de aplicativos que atuam como clientes pode aproveitar a Autenticação Moderna para obter recursos seguros. No Skype for Business Server, essa tecnologia é usada entre clientes locais e servidores locais para dar aos usuários um nível adequado de autorização aos recursos.
  
As conversas de Autenticação Moderna (que são baseadas na ADAL e no OAuth 2.0) têm alguns elementos em comum.
  
- Há um cliente fazendo uma solicitação para um recurso, nesse caso, o cliente é o Skype for Business.
    
- Há um recurso para o qual o cliente precisa de um nível específico de acesso, e esse recurso é protegido por um serviço de diretório, neste caso o recurso é o Skype for Business Server.
    
- Há uma conexão OAuth, em outras palavras, uma conexão dedicada  *a*  autorizar um usuário a acessar um recurso. (OAuth também é conhecido pelo nome mais descritivo, auth 'Servidor para Servidor' e é frequentemente abreviado como S2S.)
    
Nas conversas da Autenticação Moderna (ADAL) do Skype for Business Server, o Skype for Business Server se comunica por meio do ADFS (ADFS 3.0 no Windows Server 2012 R2). A autenticação pode acontecer usando algum outro Provedor de Identidade (IdP), mas o Skype for Business Server precisa ser configurado para se comunicar diretamente com o ADFS. Se você ainda não configurou o ADFS para funcionar com o Skype for Business Server, conclua [a instalação do ADFS.](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx)
  
A ADAL está incluída na Atualização Cumulativa de março de 2016 para o Skype for Business Server 2015, e a Atualização Cumulativa de março de 2016 para o Skype for **Business** deve ser instalada e é necessária para uma configuração bem-sucedida. Para o Skype for Business Server 2019, ele está disponível na versão inicial do produto.
  
> [!NOTE]
> Durante o lançamento inicial, a Autenticação Moderna em um ambiente local só será suportada se não houver topologia mista do Skype envolvida. Por exemplo, se o ambiente for puramente Skype for Business Server. Esta instrução pode estar sujeita a alterações. 
  
Um pacote do PowerShell incluindo arquivos .ps1 com os comandos usados pela ADAL deve ser baixado para uma configuração bem-sucedida.

Para obter informações sobre como implementar a Autenticação Moderna no Skype for Business, consulte: Como usar a Autenticação Moderna [(ADAL)](../../manage/authentication/use-adal.md) com o Skype for Business
