---
title: Operador Conexão
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 04/12/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Saiba mais sobre o Conexão, como requisitos e planejamento para implantação.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: adc229264513d7ec4ca692dca1731d7390b80dc243b4571757607c1c76b7cacb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54323943"
---
# <a name="plan-for-operator-connect"></a>Plan for Operator Conexão

>[!NOTE]
>O Conexão de operador está disponível apenas na **visualização pública.** A visualização pública permite testar os recursos futuros e fornecer comentários. Os recursos incluídos na visualização pública podem não estar completos, podem sofrer alterações e não têm suporte no Office 365 Government Cloud.

O Conexão operador é outra opção para fornecer conectividade PSTN (Rede Telefônica Pública Comutado) com Teams e Sistema de Telefonia.  

Este artigo descreve benefícios e requisitos e lista os operadores participantes do Programa Conexão Operador.  Se você decidir que o operador Conexão é a solução certa para sua organização, depois de ler este artigo, consulte [Configure Operator Conexão](operator-connect-configure.md).  

## <a name="benefits"></a>Benefícios

Com o Conexão operador, se o operador existente for um participante do programa de Conexão do Microsoft Operator, ele poderá gerenciar o serviço para trazer a chamada PSTN para Teams. O programa Conexão de operador fornece os seguintes benefícios:

- **Aproveite os contratos existentes ou encontre um novo operador.** Mantenha seu operador e contratos preferenciais ou escolha um novo de uma seleção de operadores participantes para atender às suas necessidades comerciais.

- **Infraestrutura gerenciada pelo operador.** Seu operador gerencia os serviços de chamada PSTN e controladores de borda de sessão (SBCs), permitindo que você salve na compra e gerenciamento de hardware.

- **Implantação mais rápida e fácil.** Você pode se conectar rapidamente à sua operadora e atribuir números de telefone aos usuários -– tudo a partir do Teams Admin Center.

- **Suporte e confiabilidade aprimorados.** Os operadores fornecem suporte técnico e contratos de nível de serviço compartilhados para melhorar o serviço de suporte, enquanto o peering direto do Azure cria uma conexão de rede um para um para melhorar a confiabilidade.

## <a name="requirements"></a>Requisitos

 O Conexão operador pode ser a solução certa para sua organização se:

- O Plano de Chamada da Microsoft não está disponível em sua localização geográfica.
- Seu operador preferencial é um participante do programa microsoft operator Conexão.
- Você deseja encontrar um novo operador para habilitar a chamada no Teams.

Para habilitar atribuições de números de telefone com Conexão operador, certifique-se de que seus usuários sejam:

- Teams Telefone licenciado. Para saber mais, confira [O que é Sistema de Telefonia?](what-is-phone-system-in-office-365.md) e [Atribuir Teams licenças](teams-add-on-licensing/assign-teams-add-on-licenses.md)de complemento aos usuários .
- No modo TeamsOnly. Para saber mais, consulte [Understand Microsoft Teams and Skype for Business coexistência e interoperabilidade](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

## <a name="available-operators"></a>Operadores disponíveis

Os operadores a seguir são participantes do programa Conexão Microsoft Operator:

| Operador | Recursos | Cobertura do país |
| --- | --- | --- |
| `BT`  | Chamadas | Bélgica, Dinamarca, Finlândia, França, Alemanha, Irlanda, Itália, Luxemburgo, Países Baixos, Noruega, Polônia, África do Sul, Espanha, Suécia, Suíça, Reino Unido |
| `Intrado` | Chamadas | Bélgica, Canadá, Dinamarca, França, Alemanha, Irlanda, Luxemburgo, Países Baixos, Espanha, Suécia, Reino Unido, Estados Unidos  |
| `NTT`  | Chamadas | Áustria, Bélgica, Brasil, Canadá, Tcheco, Dinamarca, Finlândia, França, Alemanha, Irlanda, Itália, Luxemburgo, México, Países Baixos, Noruega, Polônia, Portugal, Porto Rico, Romênia, África do Sul, Espanha, Suécia, Suíça, Reino Unido, Estados Unidos |
| `NuWave` | Chamadas | Áustria, Bélgica, Canadá, Dinamarca, França, Alemanha, Irlanda, Itália, Países Baixos, Portugal, Espanha, Suécia, Suíça, Reino Unido, Estados Unidos   |
| `Orange Business Services` | Chamadas | Áustria, Bélgica, Tcheca, Dinamarca, Finlândia, França, Guiana Francesa, Alemanha, Guadalupe, Irlanda, Itália, Luxemburgo, Martinica, Mayotte, Países Baixos, Noruega, Polônia, Portugal, Réunion, Saint Barthélemy, Saint Martin, Espanha, Svalbard, Suécia, Suíça, Reino Unido  |
| `Pure IP` | Chamadas | Austrália, Áustria, Bélgica, Brasil, Bulgária, Canadá, Chile, Colômbia, Croácia, Chipre, Tcheca, Dinamarca, Finlândia, França, Alemanha, Grécia, Hong Kong S.A.R., Irlanda, Itália, Japão, Lituânia, Luxemburgo, Malásia, México, Países Baixos, Nova Zelândia, Noruega, Panamá, Polônia, Portugal, Porto Rico, Romênia, Cingapura, Eslováquia, Eslovênia, África do Sul, Espanha, Suécia, Suíça, Reino Unido, Estados Unidos  |
| `Rogers Business` | Chamadas | Canadá  |
| `TATA Communications` | Chamadas | Austrália, Áustria, Bélgica, Canadá, Tcheca, Dinamarca, França, Alemanha, Hong Kong S.A.R., Hungria, Irlanda, Itália, Malásia, México, Países Baixos, Nova Zelândia, Polônia, Portugal, Romênia, Cingapura, Coreia do Sul, Espanha, Suécia, Suíça, Tailândia, Reino Unido, Estados Unidos |
| `Telekom Deutschland` | Chamadas | Alemanha  |
| `Telenor` | Chamadas | Dinamarca, Finlândia, Noruega, Suécia  |
| `Verizon` | Chamadas | Estados Unidos |
