---
title: Delegação de mensagem
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: Saiba como um usuário com o status Desalo ou Não Incomodar pode definir explicitamente outro usuário como representante em sua mensagem de status.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac23afbea7f452967718a8c2d86fd4d36584492d
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790463"
---
# <a name="message-delegation"></a>Delegação de mensagem

Um usuário já pode definir explicitamente seu status como Distância ou Não Incomodar e fornecer texto personalizado. O recurso de delegação de mensagens funciona da seguinte forma:

1. Um usuário @username menciona outro usuário em parte de uma mensagem de status de texto, sugerindo que, embora não sejam pessoas indisponíveis que querem contatá-lo, entre em contato com o @username usuário mencionado.
2. A pessoa que foi atribuída como representante será notificada de que ela foi nomeada como representante.
3. Alguém que está tentando entrar em contato com o primeiro usuário pode passar o mouse sobre o representante nomeado e facilmente enviar uma mensagem ao representante.  

Esse é um processo iniciado pelo usuário no cliente, e nenhum envolvimento do Administrador é necessário para habilitar o recurso. 

## <a name="delegation-use-scenario-in-healthcare"></a>Cenário de uso de delegação em Serviços de Saúde

*Exemplo de uso sem definir representantes:*  O Dr. Franco Piccio está de plantão no departamento de radiologia. Ele recebe uma chamada pessoal urgente e precisa se afastar pelas próximas horas. Ele pede a um de seus colegas no departamento de radiologia, Dr. Melo Ehrle, que o cubra enquanto ele estiver fora. Ele entrega informalmente o pager ao Dr. Ehrle, que está ouvindo mensagens urgentes e pings no pager e responde em nome do Dr. Piccio, além de suas responsabilidades atuais. Outras pessoas da equipe podem não perceber que a delegação informal aconteceu e a confusão se dá com os cuidados de um paciente.

*Exemplo de uso com a configuração de representantes:* O Dr. Franco Piccio está de plantão no departamento de radiologia. Ele recebe uma chamada pessoal urgente e precisa se afastar pelas próximas horas. Ele pede a um de seus colegas no departamento de radiologia, Dr. Melo Ehrle para cobrir por ele enquanto ele estiver fora. Ele altera sua mensagem de status personalizada para dizer algo semelhante a "Estou indisponível nas próximas horas. Entre em contato @DrEhrle qualquer emergência".  Outras pessoas da equipe percebem que a delegação aconteceu enquanto eles tentam entrar em contato com o Dr. Piccio, então agora eles sabem como entrar em contato com o Dr. Ehrle enquanto isso. Há pouca ou nenhuma confusão com os cuidados de um paciente.

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a>Impacto dos modos de co-existência no status do usuário no cliente do Teams

Os administradores devem estar cientes de que as anotações de status e os comportamentos de menção de delegação dependerão parcialmente do modo de co-existência de um usuário. Esta matriz mostra as possibilidades:

|Co-Existence modo | Comportamento esperado|
|---|---|
|TeamsOnly |Os usuários podem definir uma anotação somente no Teams. <br> A anotação do Teams do usuário está visível no Teams & SfB. |
|Ilhas | A anotação do usuário definida no Teams visível apenas no Teams. <br> Anotações do usuário definidas em SfB visíveis somente em SfB |
|Modos SfB* | Os usuários podem definir uma anotação somente a partir do SfB. <br> A nota SfB do usuário está visível no SfB & Teams.  |
|||

Um usuário só pode definir uma anotação no Teams se seu modo for TeamsOnly ou Islands.  

### <a name="displaying-notes-set-in-skype-for-business"></a>Exibindo anotações definidas no Skype for Business
  
Não há nenhuma indicação visual de que uma anotação foi definida do Skype for Business.

O Skype for Business não impõe um limite de caracteres nas anotações de status. O Microsoft Teams exibirá apenas os primeiros 280 caracteres de uma anotação definida pelo Skype for Business. Uma elipse (...) no final de uma anotação indica truncamento.
  
O Skype for Business não dá suporte a prazos para anotações.

A migração de anotações do Skype for Business para o Teams não é suportada quando um usuário é atualizado para o modo TeamsOnly.

## <a name="related-topics"></a>Tópicos relacionados

[Coexistência com o Skype for Business](../../coexistence-chat-calls-presence.md)
