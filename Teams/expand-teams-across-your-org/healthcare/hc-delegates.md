---
title: Delegação de mensagens
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
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: Saiba como um usuário com status Ausente ou Não Perturbe, pode definir de maneira explícita outro usuário como um delegado na sua mensagem de status.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 14f58861074ed8b9291ca725f60ff1612534f4dc
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674203"
---
# <a name="message-delegation"></a>Delegação de mensagens

Um usuário já pode definir explicitamente seu status como Ausente ou Não Incomode e fornecer textos personalizados. A função da delegação de mensagens funciona da seguinte forma:

1. Um usuário @nomedeusuário menciona outro usuário em parte de uma mensagem de status de texto, sugerindo que enquanto eles não estiverem disponíveis, pessoas que queiram contatá-los, em vez disso, contatem o usuário @nomedeusuário mencionado.
2. A pessoa que foi atribuída como representante será notificada de que foi indicada para ser a representante.
3. Alguém que tentar entrar em contato com o primeiro usuário pode passar o mouse sobre o representante indicado e facilmente enviar uma mensagem ao representante.  

Trata-se de um processo iniciado pelo usuário no cliente, e nenhum envolvimento administrativo é necessário para habilitar o recurso. 

## <a name="delegation-use-scenario-in-healthcare"></a>Cenário de uso da delegação na área da saúde

*Exemplo de uso sem definir os representantes:* O Dr. Franco Piccio está de plantão no departamento de radiologia. Ele recebe uma chamada pessoal urgente e tem que se afastar pelas próximas horas. Ele pede a uma de suas colegas do departamento de radiologia, Dra. Lena Ehrle, que o substitua enquanto ele estiver fora. Informalmente, ele entrega seu pager à Dra. Ehrle, que está ouvindo as mensagens urgentes e os pings no pager e responde-os em nome do Dr. Piccio, além das suas responsabilidades atuais. É possível que outros membros da equipe não percebam que a delegação informal aconteceu, e a confusão se instala com o cuidado de um paciente.

*Exemplo de uso definindo os representantes:* O Dr. Franco Piccio está de plantão no departamento de radiologia. Ele recebe uma chamada pessoal urgente e tem que se afastar pelas próximas horas. Ele pede a uma de suas colegas do departamento de radiologia, Dra. Lena Ehrle, que o substitua enquanto ele estiver fora. Ele altera sua mensagem de status personalizada para dizer algo semelhante a "Estou indisponível durante as próximas horas. Contatar @DraEhrle para quaisquer emergências".  Outros membros da equipe perceberam que a delegação aconteceu enquanto tentavam contatar o Dr. Piccio, e agora sabem que devem contatar a Dra. Ehrle nesse meio tempo. Pouca ou nenhuma confusão ocorre com o atendimento do paciente.

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a>Impacto dos modos de coexistência no status do usuário no cliente do Teams

Os administradores devem estar cientes de que as notas de status e as delegações mencionam comportamentos que dependerão em parte do modo de coexistência de um usuário. Esta matriz mostra as possibilidades:

|Modo de coexistência | Comportamento esperado|
|---|---|
|TeamsOnly |Os usuários podem definir uma nota apenas no Teams. <br> A nota do Teams do usuário é visível no Teams e no SfB. |
|Ilhas | O conjunto de notas do usuário no Teams é visível apenas no Teams. <br> A nota do usuário definida no SfB é visível apenas no SfB |
|Modos SfB* | Os usuários podem definir uma nota apenas no SfB. <br> A nota SfB do usuário é visível no SfB e no Teams.  |
|||

Um usuário só pode definir uma nota no Teams se seu modo for TeamsOnly ou Islands.  

### <a name="displaying-notes-set-in-skype-for-business"></a>Exibir notas definidas no Skype for Business
  
Não há nenhuma indicação visual de que uma nota tenha sido enviada pelo Skype for Business.

O Skype for Business não impõe um limite de caracteres às notas de status. O Microsoft Teams exibirá apenas os primeiros 280 caracteres de um conjunto de notas do Skype for Business. Uma elipse (...) no final de uma nota indica truncamento.
  
O Skype for Business não oferece suporte a prazos de validade para notas.

A migração de notas do Skype for Business para o Teams não possui suporte quando um usuário é atualizado para o modo TeamsOnly.

## <a name="related-topics"></a>Tópicos relacionados

[Coexistência com o Skype for Business](../../coexistence-chat-calls-presence.md)
