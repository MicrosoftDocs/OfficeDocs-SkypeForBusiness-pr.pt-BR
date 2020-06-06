---
title: Recursos de apresentador e participante em um evento do Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: Saiba mais sobre os recursos de apresentador e participante em um evento do Teams.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 7714442be770420797df1c51a532f769eb0350a4
ms.sourcegitcommit: f9db7effbb1e56484686afe4724cc3b73380166d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2020
ms.locfileid: "44565854"
---
<a name="presenter-and-participant-capabilities-in-a-teams-live-event"></a>Recursos de apresentador e participante em um evento do Teams
======================================================

Os eventos ao vivo do Microsoft Teams oferecem suporte a vários tipos de participantes. Os participantes podem acessar vários recursos de eventos ao vivo com base nas funções dentro ou fora de uma organização.

Os recursos de reunião disponíveis são:

- Bate-papo (inclui fotos e figurinhas)
- Anotações da Reunião
- Quadro de comunicações
- Gravando
- Arquivos

Este artigo descreve os recursos de participante e o que o acesso a eles têm para os recursos de evento ao vivo.

## <a name="presenters-and-organizers"></a>Apresentadores e organizadores

Apresentadores e organizadores incluem o seguinte:

- Apresentadores da minha empresa
- Apresentadores de outras organizações. Os apresentadores são designados pelo organizador e isso exige um convite pessoal do organizador.

Os apresentadores e organizadores têm acesso a todos os recursos em um evento ao vivo.

## <a name="participants"></a>Participantes

Existem vários tipos de participantes de eventos ao vivo:

- [Participante locatário](#in-tenant-participant)
- [Participante convidado](#guest-participant)
- [Participante externo (federado)](#external-federated-participant)
- [Participante anônimo](#anonymous-participant)

### <a name="in-tenant-participant"></a>Participante locatário

O participante locatário pertence à organização e tem credenciais para o locatário. Saiba mais sobre esse participante em [Segurança e o Microsoft Teams](teams-security-guide.md#participant-types).

| Evento ao vivo |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
|  **Recurso**       | Antes da reunião | Na reunião | Após a reunião |
| Chat | Não disponível | N/D | Não disponível |
| Anotações da Reunião | Sim | Sim |Sim |
| Quadro de comunicações | Sim | Sim |Sim |
| Gravando | N/A |Sim | Sim |
| Arquivos | Sim | Sim | Sim |
|||||||


### <a name="guest-participant"></a>Participante convidado

Um participante convidado é uma pessoa de outra empresa que foi convidado a acessar o Teams ou outros recursos no locatário da organização, com base na plataforma B2B do Azure Active Directory. Os usuários convidados podem ser convidados para se juntar a reuniões normais e reuniões com canal. Leia mais sobre um participante convidado no [Como é a experiência do convidado](guest-experience.md#comparison-of-team-member-and-guest-capabilities).

| Evento ao vivo  | | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **Recurso**        | Antes da reunião | Na reunião | Após a reunião |
| Chat | Não disponível | N/D | Não disponível |
| Anotações da Reunião | Sim | Sim | Sim |
| Quadro de comunicações | Não | Não | Não |
| Gravando | N/A | Não | Não |
| Arquivos | Não | Não | Não |
|||||||


### <a name="external-federated-participant"></a>Participante externo (federado)

Um participante externo é uma pessoa que está usando o Teams em outra organização e que foi convidado a participar de uma reunião, mas não tem acesso a outros recursos compartilhados da sua organização. Os participantes-usuários externos são exibidos na lista de reuniões com o mesmo nome de identidade que eles têm em sua própria organização. Leia mais sobre um participante externo em [Comunicar-se com usuários de outras empresas](communicate-with-users-from-other-organizations.md#external-access).

| Evento ao vivo |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
|  **Recurso**         | Antes da reunião | Na reunião | Após a reunião |
| Chat | Não disponível| N/D | Não disponível |
| Anotações da Reunião | Não | Não | Não |
| Quadro de comunicações | Não| Não | Não |
| Gravando | N/A | Não | Não |
| Arquivos | Sim | Sim | Sim |
|||||||

### <a name="anonymous-participant"></a>Participante anônimo

O participante anônimo é como um usuário externo, mas a identidade dele não é projetada na reunião. No momento de ingressar, eles inserem manualmente um apelido. Saiba mais sobre um participante anônimo em [Segurança e o Microsoft Teams](teams-security-guide.md#participant-types).

| Evento ao vivo|  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **Recurso**        | Antes da reunião | Na reunião | Após a reunião |
| Chat | Não disponível | N/D | Não disponível |
| Anotações da Reunião | N/A | Não | N/A |
| Quadro de comunicações | Não disponível | N/D | Não disponível |
| Gravando | N/A | Não | N/A |
| Arquivos | N/A | Não | N/A |
|||||||


## <a name="related-topics"></a>Tópicos relacionados

[Segurança e o Microsoft Teams](teams-security-guide.md)

[Acesso de convidados ao Teams](guest-access.md)

[Planejar eventos ao vivo no Teams](teams-live-events/plan-for-teams-live-events.md)
