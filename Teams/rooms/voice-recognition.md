---
title: Controle de Administração de Locatários para reconhecimento de voz (perfil de voz) no Salas do Teams
author: dstrome
ms.author: dstrome
ms.reviewer: parisataheri
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba mais sobre o controle de Administração de Locatários para reconhecimento de voz (perfil de voz) nas salas de reunião do Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9052812a669a808536cbd0179d6c16b9228296c4
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270036"
---
# <a name="manage-voice-recognition-technology-controls-for-an-intelligent-speaker"></a>Gerenciar controles de tecnologia de reconhecimento de voz para um Alto-falante Inteligente

Um Orador Inteligente usa informações de perfil de voz para reconhecer quem disse o que na transcrição ao vivo. Quando uma Salas do Microsoft Teams de reunião do Windows é equipado com um Orador Inteligente, a transcrição ao vivo pode ser usada durante a reunião. Este artigo explica como você, um administrador de locatários, controla a criação de perfil de voz usada para o reconhecimento de voz gerar transcrição ao vivo. Você pode controlar até que ponto a organização está usando o reconhecimento de voz e os seguintes recursos:

- Edite o nome do orador nas transcrições.
- Altere o locutor de um único enunciado na transcrição ou altere o orador em todos os enunciados na transcrição (mas não em transcrições futuras).
- Altere a identificação do locutor para as pessoas listadas na reunião.
- Remova a identificação de um ou mais enunciados identificados como esse locutor, em cada transcrição.

## <a name="review-intelligent-speaker-requirements"></a>Examinar os requisitos do Locutor Inteligente

Um Alto-falante Inteligente inclui uma matriz especial de sete microfones. O sistema usa informações de perfil de voz para identificar vozes de até 10 pessoas em salas de reunião.

Os seguintes itens são requisitos de Alto-falante Inteligente:

- A sala de reunião deve ter no máximo 10 pessoas presentes pessoalmente.
- A sala de reunião tem um link de upload de no mínimo 7 Mbps.

Há suporte para alto-falantes inteligentes Epos, Sennheiser e Yealink.

> [!NOTE]
> O Intelligent Speaker está disponível em todos os países e regiões. Consulte [localidades com suporte](#supported-locales) para obter uma lista das localidades com suporte no momento para registro biométrico e transcrição na reunião.

## <a name="set-up-an-intelligent-speaker"></a>Configurar um alto-falante inteligente

Um Alto-falante inteligente conecta-se diretamente usando USB ao Salas do Teams console.

> [!NOTE]
> Um Alto-falante Inteligente Yealink **deve** ser usado com um console Yealink.

> [!NOTE]
> Não há suporte para um Orador Inteligente conectado à Logitech Surface Pro Salas do Microsoft Teams. Há um problema conhecido que Salas do Teams pode reconhecer o Orador Inteligente por meio do dock.

Um Alto-falante Inteligente deve ser colocado a pelo menos 8 polegadas (20 cm) de distância de paredes e objetos grandes, como laptops. Se o cabo USB do Alto-falante Inteligente não for longo o suficiente para sua configuração, use estendadores de cabo.

1. Entre no console como administrador.
2. Defina as configurações de dispositivo do Teams para corresponder ao microfone e ao alto-falante do Alto-falante Inteligente.
   Você também pode fazer isso por meio do portal do TAC em vez de no console da sala.

   O diagrama mostra como o Alto-falante Inteligente estará conectado ao dispositivo se o dispositivo incluir uma caixa de dados.

   ![A configuração do Alto-falante Inteligente com o alto-falante, a energia e a caixa de dados. Uma linha vai para a porta USB do console e a outra linha vai para a energia.](../media/intelligent-speakers1.png)

   O diagrama mostra como o Alto-falante Inteligente estará conectado ao dispositivo se o dispositivo não incluir uma caixa de dados.

   ![A configuração do Alto-falante Inteligente com o alto-falante conectando-se diretamente ao console.](../media/intelligent-speakers2.png)

> [!Note]
> Os dispositivos EPOS e Yealink devem ter o prefixo "EPOS" ou "Yealink" e conter "UAC2_RENDER" no nome do alto-falante e "UAC2_TEAMS" no nome do microfone. Se você não encontrar esses nomes de microfone e alto-falante no menu suspenso, reinicie o dispositivo de Alto-falante Inteligente.

## <a name="enable-an-intelligent-speaker-user-recognition"></a>Habilitar um reconhecimento de usuário do Intelligent Speaker

Os dados do perfil de voz podem ser usados em qualquer reunião com um Locutor Inteligente. Consulte [as políticas de reuniões do Teams](../meetings-policies-recording-and-transcription.md#allow-transcription) e [os cmdlets](/powershell/module/skype/set-csteamsmeetingpolicy) de reunião do PowerShell para obter informações sobre as configurações da reunião.

Os dados de perfil de voz do usuário são criados quando a política é definida para distinguir ou um convidado que não é da reunião entra durante a reunião. Os dados do perfil de voz são ignorados no final da reunião.

A seguir estão as políticas necessárias para definir um Locutor Inteligente e o reconhecimento de usuário.

|Política|Descrição|Valores e comportamento|
|-|-|-|
|enrollUserOverride|Use para definir a captura de perfil de voz ou o registro nas configurações do Teams para um locatário. |**Desabilitado**<br><ul><li> Os usuários que nunca se registraram não podem exibir, registrar ou registrar novamente.<li>O ponto de entrada para o fluxo de registro ficará oculto.<li>Se os usuários selecionarem um link para a página de registro, eles verão uma mensagem informando que esse recurso não está habilitado para sua organização.  <li>Os usuários registrados podem exibir e remover seu perfil de voz nas configurações do Teams. Depois de remover o perfil de voz, eles não poderão exibir, acessar ou concluir o fluxo de registro.</li></ul><br>**Habilitado**<br><ul><li> Os usuários podem exibir, acessar e concluir o fluxo de registro.<li>O ponto de entrada será exibido na página de configurações do Teams na **guia Reconhecimento** .</li></ul>|
|roomAttributeUserOverride|Controlar a identificação do usuário baseada em voz nas salas de reunião. Essa configuração é necessária para Salas do Teams contas.| **Desativado**<br><ul><li>O Salas do Teams dispositivo não enviará largura de banda de salvamento de fluxo de áudio da sala. <li>Os usuários da sala de reunião não serão atribuídos ou diferenciados e suas assinaturas de voz não serão recuperadas nem usadas.<li>Os usuários da sala de reunião são desconhecidos.</li></ul> <br>**Atributo**<br><ul><li>Os usuários de salas serão atribuídos com base no status do registro.<li>Os usuários registrados são mostrados com seu nome na transcrição.  <li>Os usuários que não estão registrados são mostrados como Locutor \<n>.<li>O Salas do Teams dispositivo enviará sete fluxos de áudio da sala.</ul> <br>**Distinguir**<br> <ul><li>Os usuários das salas serão diferenciados e separados como locutor 1, alto-falante 2, .... locutor \<n> na transcrição.</li><li>Independentemente do status de registro do usuário, seu nome não será exibido na transcrição.</li><li>O Salas do Teams dispositivo enviará sete fluxos de áudio da sala.</li></ul>
|AllowTranscription|Necessário para contas de usuário e salas do Teams.|**True** e **False**|
||||

No centro de administração do Teams, defina a **política de Transcrição** . As configurações **estão desativadas** por padrão.

![o centro de administração com as políticas de reunião realçadas e Permitir transcrição selecionada.](../media/allow-transcription1.png)
  
> [!NOTE]
> Depois que uma política é atribuída, ela pode levar até 48 horas para entrar em vigor. Para que a política entre em vigor mais cedo, as contas devem ser assinadas e conectadas novamente.

## <a name="frequently-asked-questions-faq"></a>Perguntas frequentes (FAQ)

**Onde os dados do perfil de voz são armazenados?**

Os dados do perfil de voz são armazenados Office 365 nuvem com conteúdo do usuário.

**Qual é a linha do tempo e a política de retenção?**

A política de retenção geral é declarada na visão geral [de retenção de dados](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview). Além disso, os dados de perfil de voz de um usuário serão excluídos após 1 ano se o usuário não for convidado para nenhuma reunião com um Orador Inteligente dentro desse período de 1 ano. Os dados não são usados em nenhuma reunião para funcionários existentes. Se um funcionário tiver saído da empresa, os dados do perfil de voz serão considerados conteúdo do usuário e serão tratados como tal de acordo com Office 365 de retenção de dados descrita na visão geral [de retenção de dados](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).

**Os dados de perfil de voz são usados nos serviços da Microsoft?**

Não, os dados do perfil de voz só são usados para a finalidade para a qual o usuário forneceu consentimento. A Microsoft não usará os dados do perfil de voz, exceto em cenários de reconhecimento de voz do Teams.

Por exemplo, a Microsoft não usará os dados nas seguintes situações:

**Meus dados de perfil de voz são usados quando ingresso em uma reunião em outra organização?**

Não apenas em reuniões organizadas por um usuário em sua organização.

**Como exportar meu perfil de voz?**

O administrador de TI pode exportar seus dados de áudio a qualquer momento.

## <a name="supported-locales"></a>Localidades com suporte

As seguintes localidades de registro e transcrição na reunião têm suporte em todos os países e regiões.

### <a name="enrollment-locales"></a>Localidades de registro

Os usuários finais podem registrar suas vozes para reconhecimento nas seguintes localidades:

|**Idioma**|**País/Região**|**ID de cultura**|
|:-----|:-----|:-----|
|Inglês  <br/> |Austrália <br/> |en-AU  <br/> |
|Inglês  <br/> |Canadá  <br/> |en-CA <br/> |
|Inglês  <br/> |Índia  <br/> |en-IN  <br/> |
|Inglês  <br/> |Nova Zelândia  <br/> |en-NZ  <br/> |
|Inglês  <br/> |Reino Unido  <br/> |en-GB  <br/> |
|Inglês  <br/> |Estados Unidos  <br/> |en-US  <br/> |


### <a name="in-meeting-transcription-locales"></a>Localidades de transcrição na reunião

Depois que um usuário final se registra, sua voz pode ser reconhecida durante as reuniões e identificada na transcrição quando a reunião é definida como uma das seguintes localidades:

|**Idioma**|**País/Região**|**ID de cultura**|
|:-----|:-----|:-----|
|Chinês (Simplificado)  <br/> |China  <br/> |zh-CN  <br/> |
|Inglês  <br/> |Austrália <br/> |en-AU  <br/> |
|Inglês  <br/> |Canadá  <br/> |en-CA <br/> |
|Inglês  <br/> |Índia  <br/> |en-IN  <br/> |
|Inglês  <br/> |Nova Zelândia  <br/> |en-NZ  <br/> |
|Inglês  <br/> |Reino Unido  <br/> |en-GB  <br/> |
|Inglês  <br/> |Estados Unidos  <br/> |en-US  <br/> |
|Francês  <br/> |Canadá  <br/> |fr-CA  <br/> |
|Francês  <br/> |França  <br/> |fr-FR  <br/> |
|Alemão  <br/> |Alemanha  <br/> |de-DE  <br/> |
|Italiano  <br/> |Itália  <br/> | it-IT <br/> |
|Japonês  <br/> |Japão  <br/> |ja-JP  <br/> |
|Coreano  <br/> |Coreia  <br/> |ko-KR  <br/> |
|Português  <br/> |Brasil  <br/> |pt-BR  <br/> |
|Espanhol  <br/> |México  <br/> |es-MX  <br/> |
|Espanhol  <br/> |Espanha  <br/> |es-ES  <br/> |

## <a name="related-topics"></a>Tópicos relacionados

[Artigo de suporte: Usar alto-falantes inteligentes para identificar participantes da sala ](https://support.microsoft.com/office/use-teams-intelligent-speakers-to-identify-in-room-participants-in-meeting-transcription-a075d6c0-30b3-44b9-b218-556a87fadc00)
