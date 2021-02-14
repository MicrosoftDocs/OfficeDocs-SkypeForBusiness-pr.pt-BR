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
description: Tópicos de planejamento para autenticação e autorização para o Skype for Business Server, incluindo integração com outros produtos
ms.openlocfilehash: c657a2b3609c5fb93f7f915c460cd3334f7fac03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816241"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>Discutir autenticação e autorização no Skype for Business

Autenticação e autorização são conceitos relacionados, mas fazem um trabalho diferente para você (embora ambos sejam necessários). Em termos simples, a authenciação (AuthN) depende de segredos que apenas um usuário válido conhece ou tem, e isso pode ser uma senha, código, impressão digital, certificado, uma combinação de declarações sobre o usuário que são verdadeiras ou uma combinação dessas coisas usadas juntas. AUthN é um processo para provar que você é quem diz ser.

A autorização (AuthZ) se preocupa com o que você tem acesso depois de provar quem é. Ele determina o que você tem permissão para ver, editar e acessar de outra forma. Por exemplo, você pode ter um acesso poderoso de Administrador de Conjunto de Sites ao SharePoint Online, mas se mudar para outra carga de trabalho online, como o Skype for Business Online, você pode ter privilégios para solucionar problemas do usuário, não alterar a configuração do servidor ou servidores. Em uma terceira carga de trabalho, como o Exchange Online, você pode ter apenas o acesso médio do usuário. A AuthZ verifica o que e quanto acesso você tem para serviços/cargas, aplicativos, arquivos e outros dados.

Nossos exemplos envolvem propriedades online como o SharePoint e o Exchange online, mas os processos de AuthN e AuthZ funcionam no local e em um local híbrido da mesma maneira. Por fim, ferramentas como o AAD Connect e o ADFS se envolvem na história da AuthN e da AuthZ sincronizando contas locais e senhas no AD da nuvem (que é o Azure AD) ou atrapalhando o fluxo da AuthZ para que um usuário não seja frequentemente solicitado a solicitar suas credenciais, digamos, ao alternar entre cargas de trabalho na nuvem, criando cenários de Sign-On único. Mas eles não são, em si, responsáveis por AuthN ou AuthZ, apenas parte da mecânica.

Hoje, muitas tecnologias consideram esses processos (AuthN e AuthZ) como um mecanismo, e você ouvirá muitas referências ao processo de autenticação que também incluem autorização neles. É importante lembrar que a primeira etapa no acesso do usuário é a AuthN, provando que você é quem diz ser e que a AuthZ usa o conhecimento de quem o usuário é para determinar ao que ele tem acesso (como você verá com Open Authorization ou OAuth).

  
## <a name="authentication-and-authorization-planning-topics"></a>Tópicos de planejamento de autenticação e autorização

[Como usar a Autenticação Moderna (ADAL) com o Skype for Business](plan-adal.md)

[Topologias do Skype for Business compatíveis com a Autenticação Moderna](topologies-supported.md)

[Planejamento para desativar os métodos de autenticação herdam interna e externamente para sua rede.](turn-on-modern-auth.md)

