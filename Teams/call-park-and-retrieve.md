---
title: Estacionamento de chamada e recuperar em Teams da Microsoft
ms.author: lolaj
author: lolaj
manager: serdars
ms.date: 12/13/2018
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service:
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Use o estacionamento de chamada e recuperação para colocar uma chamada em espera no serviço de equipes na nuvem.
ms.openlocfilehash: 02ec2b3af52cac65f82f5f0f0fc2b4b54ae61369
ms.sourcegitcommit: 5f7e078125f810a9e9a89052854ef63916afe7d3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2018
ms.locfileid: "27283155"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Estacionamento de chamada e recuperar em Teams da Microsoft

Estacionamento de chamada e recuperação é um recurso que permite ao usuário colocar uma chamada em espera no serviço de equipes na nuvem. Quando uma chamada estiver estacionada, o serviço gera um código exclusivo para recuperação de chamada. O usuário que a colocou a chamada ou outra pessoa, em seguida, pode usar esse código e um dispositivo ou aplicativo suportados para recuperar a chamada. 

Estes são alguns dos cenários comuns para o uso de estacionamento de chamada: 

- Um recepcionista parques uma chamada para alguém trabalhando em uma fábrica. O recepcionista comunica a chamada e o número de código sobre o sistema de endereço público. Em seguida, o usuário que a chamada é para pode Pegue um telefone de equipes na fábrica e digite o código para recuperar a chamada.
- Um usuário parques uma chamada em um dispositivo móvel, pois a bateria do dispositivo está ficando sem energia. O usuário pode digitar então de código para recuperar a chamada de um telefone de mesa de equipes.
- Um parques representante de suporte um cliente chamar e envia um anúncio em um canal de equipes para um especialista recuperar a chamada e ajudar o cliente. Com um perito indica o código nos clientes de equipes para recuperar a chamada

> [!IMPORTANT]
> Este recurso só está disponível no modo exclusivo para as equipes de implantação. Para obter mais detalhes sobre modos de implantação de equipes, consulte [entender as equipes da Microsoft e Skype para interoperabilidade e coexistência de negócios](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>É necessária uma licença

Para estacionar e recuperar chamadas, um usuário deve ser um usuário do Enterprise Voice e um administrador deve conceder ao usuário uma política de estacionamento de chamada. Para obter detalhes adicionais sobre o modelo de licenciamento, consulte [Licenciamento do Office 365 para equipes da Microsoft](office-365-licensing.md).

## <a name="call-park-and-retrieve-feature-availability"></a>Estacionamento de chamada e recuperar a disponibilidade de recursos

Estacionamento de chamada e recuperação no momento é suportado pelos seguintes clientes e dispositivos. (Suportado no equipes somente modo, com ou sem conectividade PSTN).

| Recurso | Área de trabalho de equipes | As equipes Mac App | As equipes Web App (borda) |As equipes móveis iOS/Android App | Telefone IP de equipes | Skype para negócios IP phone |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| Estacionar uma chamada | Sim | Sim | Sim | Em breve | Em breve| Não |
| Recuperar uma chamada estacionada | Sim | Sim | Sim | Em breve | Em breve| Não |
| Toque de chamada não recuperados novamente | Sim | Sim | Sim | Em breve | Em breve| Não |

## <a name="configuring-call-park-and-retrieve"></a>Configurando o estacionamento de chamada e recuperação

Você deve ser um administrador para configurar o estacionamento de chamada e recuperação, e o recurso é desabilitado por padrão. Você pode habilitá-lo para usuários e criar grupos de usuários usando a diretiva de estacionamento de chamada. Quando você aplica a mesma política a um conjunto de usuários, eles poderão estacionar e recuperar chamadas entre si. Para configurar o estacionamento de chamadas para usuários e criar grupos de usuários de estacionamento de chamada, siga o procedimento abaixo.

Para obter informações sobre como usar o estacionamento de chamada e recuperar um recurso, consulte [estacionamento de uma chamada em equipes](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).

### <a name="configure-call-park-and-retrieve-with-powershell"></a>Configurar o estacionamento de chamada e recuperar com o PowerShell

Use o cmdlet [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) do PowerShell para criar uma política de estacionamento de chamada.

Use o cmdlet [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) do PowerShell para conceder uma política de estacionamento de chamada.

## <a name="troubleshooting"></a>Solução de problemas

Se os usuários não podem ver o estacionamento ou recuperar botão: 

- Verifique se o usuário tem a diretiva de estacionamento de chamada ativada. 

Se um usuário tenta recuperar uma chamada e for bem sucedido, verifique o seguinte:

- Verificar se o usuário está usando o cliente de equipes ou um equipes dispositivo/telefone habilitado
- Agrupamento – é o usuário membro do grupo de estacionamento de chamada?
- Modo de ilha – estacionamento de chamada e recuperar não está disponível no modo de ilha de equipes.
- A chamada já foi recuperada ou encerrada.

## <a name="more-information"></a>Mais informações

[Estacionamento de uma chamada em equipes](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).