---
title: Criando um fluxo no Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: asteele
search.appverid: MET150
f1.keywords:
- NOCSH
description: Este artigo percorrerá a criação de um fluxo para eventos de streaming do Microsoft Teams.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: b7ff5d15a08f186ae59ccef65fcd8280d84237d1
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767914"
---
# <a name="create-a-live-event-in-microsoft-teams"></a>Criar um evento ao vivo no Microsoft Teams

> [!IMPORTANT]
> **China**: atualmente, os usuários localizados na China não poderão configurar ou participar de eventos ao vivo do Microsoft Teams ou do Yammer ou exibir vídeos sob demanda sem a ajuda do administrador de TI.
>
> Antes de começar, verifique com o administrador se ele precisa configurar uma VPN para conectar sua rede corporativa para que esses aplicativos possam funcionar perfeitamente em sua organização.

> [!IMPORTANT]
> Ao configurar um evento ao vivo, recomendamos que você configure suas permissões de vídeo, comunidade e usuário pelo menos 24 horas antes do evento para obter a melhor experiência. Isso inclui configurações como adicionar usuários, atualizar permissões de vídeo e alterar uma comunidade de privada para pública. Pode levar até duas (duas) horas para que determinadas alterações se propagassem entre Microsoft Stream, Microsoft Teams e Microsoft Yammer. Permitir 24 horas ou mais pode fornecer tempo para testar e fazer ajustes, se necessário.

## <a name="schedule-the-live-event"></a>Agendar o evento ao vivo

1. Abra o cliente do Microsoft Teams e acesse o calendário.
1. Use a lista suspensa **Nova reunião** .
1. Selecione a opção **Evento ao vivo** .
1. Na janela pop-up **Novo evento ao vivo** , insira os detalhes do evento à esquerda (**Título**, **Local**, **Início**, **Término**, **Fuso Horário** e **Detalhes**).
1. Na mesma página, à direita, **convide os apresentadores** para adicionar apresentadores e produtores, individualmente ou por meio de grupos.
1. Quando tudo for inserido, selecione **Avançar**.
1. Selecione **Pessoas e grupos**, **em toda a organização** ou **público** em **permissões de evento ao vivo** para especificar quem pode assistir ao evento ao vivo.
1. Selecione **Codificador do Teams (versão prévia)** em **Como você produzirá seu evento ao vivo**?
1. Configure opções necessárias como **Q&A**, **Legendas e outras** em **Opções de evento**.
1. Selecione **Agendar** para concluir o agendamento do evento ao vivo.

## <a name="stream-the-live-event"></a>Transmitir o evento ao vivo

1. Depois de agendar seu evento ao vivo, você pode recuperar a **URL de ingestão de servidor RTMP** e a **Chave RTMP** sob o **RTMP Na seção de detalhes** do convite de calendário, que você pode usar para enviar o conteúdo do Codificador por meio da Ingestão RTMP.
1. Para configurar o codificador, copie a URL de ingestão RTMP e a Chave RTMP no codificador para começar a enviar o feed do codificador ao vivo para a Equipe. Usar um codificador para transmissão ao vivo no Microsoft Teams tem mais informações.
1. Usando um cliente do Microsoft Teams, participe do evento ao vivo como produtor. Você também pode encontrar o RTMP Em detalhes de mais opções de reunião ->.
1. Ao começar a enviar conteúdo por push do codificador para o ponto de ingestão do servidor, você deverá ver a atualização de visualização do produtor.
1. Depois de ficar satisfeito com a configuração e ver a visualização na interface do usuário do produtor, selecione o **feed RTMP** nas fontes e **Envie Ao Vivo**.
1. Selecione **Iniciar evento** para iniciar o evento ao vivo, poste quais membros da plateia podem ver o evento.
1. Quando terminar o evento, selecione **Encerrar evento** na interface do usuário do produtor. Isso encerra o evento e disponibiliza o conteúdo imediatamente para vídeo sob demanda.

Para obter mais informações sobre como transmitir o evento ao vivo, examine [Produzir um evento ao vivo usando o codificador do Teams](https://support.microsoft.com/office/produce-a-teams-live-event-using-teams-encoder-b0026c9d-fd37-4bb3-bffc-6961f221fbe9).
