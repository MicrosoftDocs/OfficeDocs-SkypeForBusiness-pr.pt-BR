---
title: Planejamento da autenticação moderna (ADAL) com Skype para negócios
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: Este artigo explica o que é autenticação moderno (que se baseia na biblioteca de autenticação do Active Directory (ADAL) e OAuth 2.0).
ms.openlocfilehash: 666808134e2ed178a85058a6e3cd3019bf982a35
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907189"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>How to use Modern Authentication (ADAL) with Skype for Business
 
Este artigo apresenta moderno autenticação (que se baseia na biblioteca de autenticação do Active Directory (ADAL) e OAuth 2.0) que podem ser encontradas no de 2016 março atualização cumulativa do Skype for Business para Skype para Business Server 2015 ou inicial versão do Skype Business Server 2019.
  
## <a name="what-is-adal"></a>O que é ADAL?

ADAL é o acrônimo de “Biblioteca de Autenticação do Active Directory" e, junto com o OAuth 2.0, constitui a base da Autenticação Moderna. Esta biblioteca de código foi projetada para disponibilizar recursos protegidos em seu diretório para aplicativos de cliente (como Skype para negócios) por meio de tokens de segurança. A ADAL interage com o OAuth 2.0 para habilitar mais cenários de autenticação e autorização, como MFA (Multi-factor Authentication), bem como mais formas de Autenticação de SAML.
  
Vários aplicativos que atuam como clientes podem aproveitar a Autenticação Moderna para obter recursos seguros. No Skype para Business Server, essa tecnologia é usada entre clientes locais e servidores locais para fornecer aos usuários um nível adequado de autorização para recursos.
  
As conversas de Autenticação Moderna (que se baseiam em ADAL e OAuth 2.0) têm alguns elementos em comum.
  
- Não há um cliente fazendo uma solicitação para um recurso, nesse caso, o cliente for Skype para negócios.
    
- Não há um recurso no qual o cliente precisa de um nível específico de acesso, e esse recurso esteja protegido por um serviço de diretório, nesse caso, o recurso é Skype para Business Server.
    
- Não há uma conexão de OAuth, em outras palavras, uma conexão que é dedicada a *autorização de* um usuário para acessar um recurso. (OAuth também é conhecido pelo nome mais descritivo, autenticação "Servidor a Servidor' e é frequentemente abreviado como S2S.)
    
Skype para conversas Business Server moderno autenticação (ADAL), Skype para Business Server comunica-se por meio do ADFS (ADFS 3.0 no Windows Server 2012 R2). A autenticação pode ser feita usando-se algum outro IdP (Provedor de Identidade), mas o Skype for Business Server precisa ser configurado para se comunicar com o ADFS diretamente. Se você ainda não tiver configurado o ADFS para trabalhar com Skype para Business Server complete a [instalação do ADFS](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).
  
ADAL está incluído no de 2016 março atualização cumulativa do Skype para Business Server 2015 e o de 2016 março atualização cumulativa do Skype para negócios **deve** ser instalada e é necessária para que a configuração bem-sucedida. Para Skype para Business Server 2019, é disponível na versão inicial do produto.
  
> [!NOTE]
> Durante a versão inicial, a autenticação moderna em um ambiente local é suportada apenas se não houver nenhuma topologia mista do Skype envolvidos. Por exemplo, se o ambiente é puramente Skype para Business Server. Esta declaração pode ser está sujeita a alterações. 
  
Um pacote do PowerShell incluindo arquivos .ps1 com os comandos usados por ADAL deve ser baixado para a configuração com êxito.

Para obter informações sobre como implementar autenticação moderno em Skype for Business, consulte: [como usar moderno autenticação (ADAL) com Skype para negócios](../../manage/authentication/use-adal.md)
