---
title: Exigir criptografia de ponta a ponta para reuniões confidenciais do Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: Saiba como habilitar a criptografia de ponta a ponta para reuniões do Teams.
ms.openlocfilehash: 091da268e8042707dd7e27094fde33d957a52d79
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800143"
---
# <a name="require-end-to-end-encryption-for-sensitive-teams-meetings"></a>Exigir criptografia de ponta a ponta para reuniões confidenciais do Teams

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

A criptografia de ponta a ponta é a criptografia de informações em sua origem e descriptografia em seu destino pretendido sem a capacidade de descriptografar nós intermediários. Quando as reuniões no Teams são criptografadas de ponta a ponta, ninguém, exceto os participantes da reunião, pode ouvir ou ver a comunicação. Nenhum outro grupo, incluindo a Microsoft, tem acesso à conversa descriptografada.

Reuniões criptografadas de ponta a ponta podem ser feitas entre duas partes quando: as partes estão usando a versão mais recente do cliente da área de trabalho do Teams para Windows ou Mac, elas estão em um dispositivo móvel com a atualização mais recente para iOS e Android, ou estão em um Salas do Teams no dispositivo Windows usando a atualização mais recente. Não há suporte para criptografia de ponta a ponta para a reunião atendida por meio do navegador.

> [!Note]
> A criptografia de reunião de ponta a ponta requer Teams Premium.

Se você não habilitar a criptografia de ponta a ponta, o Teams ainda garantirá reuniões usando criptografia com base nos padrões do setor. Os dados trocados durante as reuniões são sempre seguros durante o trânsito e em repouso. Para obter mais informações, consulte [Criptografia de mídia para o Teams](teams-security-guide.md#media-encryption).

Durante uma reunião criptografada de ponta a ponta, o Teams protege os seguintes recursos:

- Áudio

- Vídeo

- Compartilhamento de tela

[A criptografia no Microsoft 365](/microsoft-365/compliance/encryption) protege chat, compartilhamento de arquivos, presença e outros conteúdos na reunião. Aplicativos, avatares, reações, chat e Q&A não são criptografados de ponta a ponta.

Os seguintes recursos não estão disponíveis durante uma reunião criptografada de ponta a ponta:

- Legendas ao vivo e transcrição

- Gravando

- Modo juntos, modo complementar, galeria grande

- Salas para sessão de grupo

Se sua organização usar a gravação de conformidade, a criptografia de ponta a ponta não estará disponível. Para obter mais informações sobre como o Teams dá suporte à gravação de conformidade, consulte [Introdução à gravação baseada em políticas do Teams para chamadas e reuniões](teams-recording-policy.md).

## <a name="enable-end-to-end-encryption-for-meetings"></a>Habilitar a criptografia de ponta a ponta para reuniões

Por padrão, a criptografia de ponta a ponta para reuniões não está habilitada. Você pode habilitá-lo usando uma política de criptografia aprimorada de administrador do Teams.

Depois que a criptografia de ponta a ponta é habilitada, os organizadores da reunião têm a opção de escolher a criptografia de ponta a ponta e criam uma reunião. Você também pode impor a criptografia de ponta a ponta usando um modelo de reunião ou um rótulo de confidencialidade.

Para habilitar a criptografia de ponta a ponta para reuniões

1. No centro de administração do Teams, selecione **Política de criptografia aprimorada**.

1. Selecione a política que você deseja atualizar.

1. Defina **a criptografia de reunião de ponta a ponta** como **Não habilitada, mas os usuários podem substituir**.

1. Selecione **Salvar**.

## <a name="related-topics"></a>Tópicos relacionados

[Configurar reuniões do Teams com três camadas de proteção](configure-meetings-three-tiers-protection.md)

[Use criptografia de ponta a ponta para chamadas um-para-um do Microsoft Teams](teams-end-to-end-encryption.md)
