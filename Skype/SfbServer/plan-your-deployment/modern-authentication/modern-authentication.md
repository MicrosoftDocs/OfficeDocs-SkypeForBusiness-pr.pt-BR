---
title: Planejar a autenticação moderna no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: Planejamento de tópicos para autenticação e autorização para o Skype for Business Server, incluindo a integração com outros produtos
ms.openlocfilehash: 3b673a9f88895ac57277ef51b51fe0a4a27c64a2
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221575"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>Discutir a autenticação e a autorização no Skype for Business

A autenticação e a autorização são conceitos relacionados, mas não funcionam diferentes para você (embora ambos sejam necessários). Resumir os termos simples, Authenciation (Authn) depende dos segredos apenas de um usuário válido conhece ou tem e que pode ser uma senha, código, impressão digital, certificado, uma combinação de declarações sobre o usuário que é verdadeira ou uma combinação dessas coisas usadas em conjunto. Authn é um processo para provar que você é quem diz ser.

Autorização (AuthZ) é preocupado com o que você tem acesso depois de comprovar quem é você. Ele determina o que você tem permissão para ver, editar e acessar o caso. Por exemplo, você pode ter um poderoso acesso de administrador do conjunto de sites ao SharePoint Online, mas se você alternar para outra carga de trabalho online, como o Skype for Business Online, você pode ter os privilégios para solucionar problemas de usuário, não alterar a configuração do servidor ou servidores. Em uma terceira carga de trabalho, como o Exchange Online, você pode ter apenas o acesso do usuário médio. A AuthZ verifica o que é e quanto acesso você tem a serviços/worloads, aplicativos, arquivos e outros dados.

Nossos exemplos envolvem Propriedades online, como o SharePoint e o Exchange Online, mas os processos de Authn e AuthZ trabalham no local e em um local híbrido da mesma maneira. Em última análise, as ferramentas como o AAD Connect e o ADFS se envolvem na autenticação de contas e senhas locais no AD da nuvem (que é o AD do Azure) ou invasos no fluxo de AuthZ para que um usuário não tenha suas credenciais freqüentemente solicitadas, digamos ao alternar entre cargas de trabalho na nuvem, criando cenários de logon único. Mas eles não são, sozinhos, Authn ou AuthZ, apenas parte da mecânica.

Hoje, muitas tecnologias consideram esses processos (Authn e AuthZ) como um mecanismo, e você ouvirá muitas referências a processos de autenticação que também incluem autorização neles. É importante lembrar que a primeira etapa no acesso do usuário é Authn, provando que você é quem diz ser e que a AuthZ usa o conhecimento de quem o usuário deve determinar o que ele ou ela tem que acessar (como você verá com autorização aberta ou OAuth).

  
## <a name="authentication-and-authorization-planning-topics"></a>Tópicos de planejamento de autenticação e autorização

[Como usar a ADAL (autenticação moderna) com o Skype for Business](plan-adal.md)

[Topologias do Skype for Business compatíveis com a autenticação moderna](topologies-supported.md)

[Planejar a desativação de métodos de autenticação herdados interna e externamente em sua rede.](turn-on-modern-auth.md)

