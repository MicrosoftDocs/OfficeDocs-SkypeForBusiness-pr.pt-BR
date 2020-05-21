---
title: Recursos de apresentador e participante em uma reunião do Teams
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
description: Saiba mais sobre os recursos de apresentador e participante em uma reunião do Teams.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 11c5858532ade4fd4ed00f7c8f6d1d0c94baeb2d
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321730"
---
<a name="presenter-and-participant-capabilities-in-a-teams-meeting"></a>Recursos de apresentador e participante em uma reunião do Teams
======================================================

As reuniões do Microsoft Teams oferecem suporte a vários tipos de participantes. Os participantes podem acessar vários recursos de reunião baseado na sua função dentro ou fora da organização.

Os recursos de reunião disponíveis são:

- Bate-papo (inclui fotos e figurinhas)
- Anotações da Reunião
- Quadro de comunicações
- Gravando
- Arquivos
- Agendar uma reunião (somente para reuniões)

Este artigo descreve os recursos de participante e o acesso que eles têm aos recursos de reunião.

## <a name="presenters-and-organizers"></a>Apresentadores e organizadores

Apresentadores e organizadores incluem o seguinte:

- Apresentadores da minha empresa
- Apresentadores de outras organizações - isso inclui participantes anônimos e externos. Os apresentadores são designados pelo organizador e isso exige um convite pessoal do organizador.

Os apresentadores e organizadores têm acesso a todos os recursos de uma reunião ou evento ao vivo.

## <a name="participants"></a>Participantes

Existem vários tipos de participantes de reuniões:

- [Participante locatário](#in-tenant-participant)
- [Participante convidado](#guest-participant)
- [Participante externo (federado)](#external-federated-participant)
- [Participante anônimo](#anonymous-participant)

### <a name="in-tenant-participant"></a>Participante locatário

O participante locatário pertence à organização e tem credenciais para o locatário. Saiba mais sobre esse participante em [Segurança e o Microsoft Teams](teams-security-guide.md#participant-types).

|Reunião  |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **Recurso**        | Antes da reunião | Na reunião | Após a reunião |
| Chat | Sim | Sim | Sim |
| Anotações da Reunião | Sim | Sim |Sim |
| Quadro de comunicações | Sim | Sim |Sim |
| Gravando | N/A |Sim | Sim |
| Arquivos | Sim | Sim | Sim |
| Agendar uma reunião | Sim | N/D | N/A |
|||||||

### <a name="guest-participant"></a>Participante convidado

Um participante convidado é uma pessoa de outra empresa que foi convidado a acessar o Teams ou outros recursos no locatário da organização, com base na plataforma B2B do Azure Active Directory. Os usuários convidados podem ser convidados para se juntar a reuniões normais e reuniões com canal. Leia mais sobre um participante convidado no [Como é a experiência do convidado](guest-experience.md#comparison-of-team-member-and-guest-capabilities).

| Reunião |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **Recurso**        | Antes da reunião | Na reunião | Após a reunião |
| Chat | Sim | Sim | Sim |
| Anotações da Reunião | Sim | Sim | Sim |
| Quadro de comunicações | Não | Não |Não |
| Gravando | N/A |Não | Não |
| Arquivos | Sim | Sim | Sim |
| Agendar uma reunião | Não | N/D | N/A |
|||||||

### <a name="external-federated-participant"></a>Participante externo (federado)

Um participante externo é uma pessoa que está usando o Teams em outra organização e que foi convidado a participar de uma reunião, mas não tem acesso a outros recursos compartilhados da sua organização. Os participantes-usuários externos são exibidos na lista de reuniões com o mesmo nome de identidade que eles têm em sua própria organização. Leia mais sobre um participante externo em [Comunicar-se com usuários de outras empresas](communicate-with-users-from-other-organizations.md#external-access).

| Reunião (pode ser adicionada a uma equipe como apenas para convidados) ||
|-|-|-|
| **Recurso** |||
| Chat | N/A |
| Anotações da Reunião | N/A |  
| Quadro de comunicações | N/A |
| Gravando | N/A |  
| Arquivos | N/A |
| Agendar uma reunião | N/A |
|||

### <a name="anonymous-participant"></a>Participante anônimo

O participante anônimo é como um usuário externo, mas a identidade dele não é projetada na reunião. No momento de ingressar, eles inserem manualmente um apelido. Saiba mais sobre um participante anônimo em [Segurança e o Microsoft Teams](teams-security-guide.md#participant-types).

| Reunião  | | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **Recurso**        | Antes da reunião | Na reunião | Após a reunião |
| Chat | N/A | Não | N/A |
| Anotações da Reunião | N/A | Não | N/A |
| Quadro de comunicações | N/A | Não | N/A |
| Gravando | N/A | Não | N/A |
| Arquivos | N/A | Não | N/A |
| Agendar uma reunião | N/A | N/D | N/A |
|||||||

## <a name="related-topics"></a>Tópicos relacionados

[Segurança e o Microsoft Teams](teams-security-guide.md)

[Acesso de convidados ao Teams](guest-access.md)
