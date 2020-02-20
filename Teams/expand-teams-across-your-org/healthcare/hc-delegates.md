---
title: Delegação de mensagem
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: Um usuário pode definir explicitamente outro usuário como um representante na mensagem de status.
ms.openlocfilehash: e76181ff69f2d4e6ed75183bdb5fbdda695d05e4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153803"
---
# <a name="message-delegation"></a>Delegação de mensagem

Um usuário já pode definir explicitamente seu status como ausente ou não incomodar e fornecer texto personalizado. O recurso de delegação de mensagens funciona da seguinte maneira:

1. Um usuário @username mencionar outro usuário em parte de uma mensagem de status de texto, sugerindo que, enquanto eles não estiverem disponíveis, entrarem em contato com o usuário @username mencionado.
2. A pessoa que foi atribuída como representante é notificada de que foram nomeadas como um representante.
3. Alguém que está tentando entrar em contato com o primeiro usuário pode passar o mouse sobre o representante indicado e enviar facilmente o representante para a mensagem.  

Esse é um processo iniciado pelo usuário no cliente e não é necessário ter um envolvimento do administrador para habilitar o recurso. 

## <a name="delegation-use-scenario-in-healthcare"></a>Cenário de uso de delegação na área de saúde

*Exemplo de uso sem configuração de representantes:*  O Dr. Franco Piccio está on-Call no departamento da radiologia. Ele recebe uma chamada pessoal urgente e tem que deixar de entrar nas próximas horas. Ele pergunta a um de seus colegas no departamento de Radiologia, o Dr. Lena Ehrle, a cobrir para ele enquanto ele está fora. Ele, informalmente, passa pelo seu pager para o Dr. Ehrle, que está ouvindo mensagens urgentes e pings no pager e responde a ele em nome do Dr. Piccio, além de suas responsabilidades atuais. Outras pessoas na equipe podem não perceber que a delegação informal ocorreu, e confusão de Ensues com o cuidado de um paciente.

*Exemplo de uso com a configuração de representantes:* O Dr. Franco Piccio está on-Call no departamento da radiologia. Ele recebe uma chamada pessoal urgente e tem que deixar de entrar nas próximas horas. Ele pede um de seus colegas no departamento da radiologia, o Dr. Lena Ehrle para falar com ele enquanto ele está fora. Ele altera sua mensagem de status personalizado para dizer algo semelhante a "não estou disponível pelas próximas horas. Entre em contato com a @DrEhrle para qualquer emergência. "  Outras pessoas na equipe percebem que a delegação aconteceu enquanto tentavam entrar em contato com o Dr. Piccio, portanto, agora ele sabe entrar em contato com o Dr. Ehrle enquanto isso. Pouca ou nenhuma confusão Ensues com o cuidado de um paciente.

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a>Impacto dos modos de coexistência no status do usuário no cliente da equipe

Os administradores devem estar cientes de que as anotações de status e os comportamentos de referência de delegação dependerão parcialmente do modo de coexistência de um usuário. Esta matriz mostra as possibilidades:

|Modo de co-existência | Comportamento esperado|
|---|---|
|TeamsOnly |Os usuários podem definir uma anotação apenas do teams. <br> A nota de equipes do usuário é visível no Teams & SfB. |
|Ilhas | Anotação do usuário definida em equipes visíveis somente no Teams. <br> Nota do usuário definida no SfB visível apenas em SfB |
|SfB * Modes | Os usuários podem definir uma anotação apenas a partir do SfB. <br> A anotação SfB do usuário fica visível no SfB & Teams.  |
|||

Um usuário só poderá definir uma anotação no Microsoft Teams se seu modo for TeamsOnly ou ilhas.  

### <a name="displaying-notes-set-in-skype-for-business"></a>Exibir anotações definidas no Skype for Business
  
Não há indicação visual de que uma anotação foi definida no Skype for Business.

O Skype for Business não impõe um limite de caracteres nas anotações de status. O Microsoft Teams só exibirá os primeiros 280 caracteres de uma anotação definida no Skype for Business. Uma elipse (...) no final de uma nota indica truncamento.
  
O Skype for Business não dá suporte a tempos de expiração de anotações.

Não há suporte para a migração de anotações do Skype for Business para o Teams quando um usuário é atualizado para o modo TeamsOnly.

## <a name="related-topics"></a>Tópicos relacionados

[Coexistência com o Skype for Business](../../coexistence-chat-calls-presence.md)
