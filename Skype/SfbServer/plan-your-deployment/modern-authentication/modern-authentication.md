---
title: Planejar a autenticação moderna no Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: Tópicos de planejamento para autenticação e autorização para Skype for Business Server, incluindo a integração com outros produtos
ms.openlocfilehash: 0ba25ce4a1c314e2df96c1a1009254254277f4636d937fa2f14277a92976b7b8
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349923"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>Discutindo autenticação e autorização Skype for Business

Autenticação e autorização são conceitos relacionados, mas fazem trabalhos diferentes para você (embora ambos sejam necessários). Em termos simples, a authenciation (AuthN) depende de segredos que apenas um usuário válido conhece ou tem, e isso pode ser uma senha, código, impressão digital, certificado, uma combinação de declarações sobre o usuário verdadeiro ou uma combinação dessas coisas usadas em conjunto. AuthN é um processo para provar que você é quem diz ser.

A autorização (AuthZ) se preocupa com o que você tem acesso depois de provar quem você é. Ele determina o que você tem permissão para ver, editar e acessar de outra forma. Por exemplo, você pode ter acesso poderoso de Administrador de Conjunto de Sites ao SharePoint Online, mas se você mudar para outra carga de trabalho online, como o Skype for Business Online, poderá ter os privilégios para solucionar problemas do usuário, não alterar a configuração do servidor ou servidores. Em uma terceira carga de trabalho, como Exchange Online, você pode ter apenas o acesso médio do usuário. O AuthZ verifica o que e quanto acesso você tem a serviços/worloads, aplicativos, arquivos e outros dados.

Nossos exemplos envolvem propriedades online como SharePoint e Exchange online, mas os processos da AuthN e do AuthZ funcionam no local e em um local híbrido da mesma maneira. Por fim, ferramentas como o AAD Conexão e o ADFS se envolvem no AuthN e no AuthZ, sincronizando contas locais e senhas no AD do Cloud (que é o Azure AD) ou atrapalhando o fluxo do AuthZ para que um usuário não seja solicitado com frequência para suas credenciais, por exemplo, ao alternar entre cargas de trabalho na Nuvem, criando cenários de Sign-On único. Mas eles não são, em si, responsáveis pelo AuthN ou pelo AuthZ, apenas parte da mecânica.

Hoje, muitas tecnologias consideram esses processos (AuthN e AuthZ) um mecanismo e você ouvirá muitas referências ao processo de autenticação que também incluem autorização neles. É importante lembrar que a primeira etapa no acesso ao usuário é a AuthN, provando que você é quem você diz ser e que o AuthZ usa o conhecimento de quem o usuário é para determinar ao que ele tem acesso (como você verá com Autorização Aberta ou OAuth).

  
## <a name="authentication-and-authorization-planning-topics"></a>Tópicos de Planejamento de Autenticação e Autorização

[Como usar a Autenticação Moderna (ADAL) com Skype for Business](plan-adal.md)

[Topologias do Skype for Business compatíveis com a Autenticação Moderna](topologies-supported.md)

[Planejando desativar os métodos de autenticação herdou interna e externamente para sua rede.](turn-on-modern-auth.md)

