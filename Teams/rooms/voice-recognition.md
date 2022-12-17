---
title: Controle de Administração de Locatário para reconhecimento de voz (perfil de voz) em Salas do Teams
author: dstrome
ms.author: dstrome
ms.reviewer: parisataheri
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba mais sobre o controle Administração de Locatários para reconhecimento de voz (perfil de voz) nas salas de reunião do Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
appliesto:
- Microsoft Teams
ms.openlocfilehash: 478e739be2787eb2758a2070a441f68c7da727ba
ms.sourcegitcommit: b710fc61558a0e031d4e3e4000f234c495e2c4c6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2022
ms.locfileid: "69438299"
---
# <a name="manage-voice-recognition-technology-controls-for-an-intelligent-speaker"></a>Gerenciar controles de tecnologia de reconhecimento de voz para um alto-falante inteligente

Um Alto-Falante Inteligente usa informações de perfil de voz para reconhecer quem disse o que na transcrição ao vivo. Quando um Salas do Microsoft Teams na sala de reunião do Windows é equipado com um Alto-Falante Inteligente, a transcrição ao vivo pode ser usada durante a reunião. Este artigo explica como você, um administrador de locatário, controla a criação de perfil de voz usada para reconhecimento de voz para gerar transcrição ao vivo. Você pode controlar até que ponto a organização está usando o reconhecimento de voz e os seguintes recursos:

- Edite o nome do orador em transcrições.
- Altere o alto-falante de um único enunciado na transcrição ou altere o alto-falante em todos os enunciados na transcrição (mas não em transcrições futuras).
- Altere a identificação do orador para as pessoas listadas na reunião.
- Remova a identificação de um ou mais enunciados identificados como esse alto-falante em cada transcrição.

## <a name="review-intelligent-speaker-requirements"></a>Examinar os requisitos do Alto-Falante Inteligente

Um Alto-Falante Inteligente inclui uma matriz especial de sete microfones. O sistema usa informações de perfil de voz para identificar vozes de até 10 pessoas em salas de reunião.

Os seguintes itens são requisitos do Alto-Falante Inteligente:

- A sala de reunião deve ter no máximo 10 pessoas presentes pessoalmente.
- A sala de reunião tem um link de carregamento de no mínimo 7 Mbps.

Há suporte para alto-falantes inteligentes Epos, Sennheiser e Yealink.

> [!NOTE]
> O Alto-Falante Inteligente está disponível em todos os países e regiões. Consulte [Localidades com suporte](#supported-locales) para obter uma lista de localidades com suporte atualmente para registro biométrico e transcrição na reunião.

## <a name="set-up-an-intelligent-speaker"></a>Configurar um alto-falante inteligente

Um Alto-Falante Inteligente se conecta diretamente usando USB ao console Salas do Teams.

> [!NOTE]
> Um Alto-Falante Inteligente do Yealink **deve** ser usado com um console do Yealink.

> [!NOTE]
> Não oferecemos suporte a um Alto-Falante Inteligente conectado ao Logitech Surface Pro Salas do Microsoft Teams. Há um problema conhecido que Salas do Teams não pode reconhecer o Alto-Falante Inteligente por meio do dock.

Um alto-falante inteligente deve ser colocado a pelo menos 20 cm de distância de paredes e objetos grandes, como laptops. Se o cabo USB do Alto-Falante Inteligente não for longo o suficiente para sua instalação, use extensores de cabo.

1. Entre no console como administrador.
2. Defina as configurações do dispositivo do Teams para corresponder ao microfone e ao alto-falante do Alto-Falante Inteligente.
   Você também pode fazer isso por meio do portal do TAC em vez de no console da sala.

   O diagrama mostra como o Alto-Falante Inteligente está conectado ao dispositivo se o dispositivo incluir uma caixa de dados.

   ![A configuração do Alto-Falante Inteligente com o alto-falante, a caixa de dados e energia. Uma linha vai para a porta USB do console, e a outra linha vai para a energia.](../media/intelligent-speakers1.png)

   O diagrama mostra como o Alto-Falante Inteligente está conectado ao dispositivo se o dispositivo não incluir uma caixa de dados.

   ![A configuração do Alto-Falante Inteligente com o alto-falante se conectando diretamente ao console.](../media/intelligent-speakers2.png)

> [!NOTE]
> Os dispositivos EPOS e Yealink devem ter o prefixo "EPOS" ou "Yealink" e conter "UAC2_RENDER" no nome do alto-falante e "UAC2_TEAMS" no nome do microfone. Se você não encontrar esses nomes de microfone e alto-falante no menu suspenso, reinicie o dispositivo Do Alto-Falante Inteligente.

## <a name="enable-an-intelligent-speaker-user-recognition"></a>Habilitar um reconhecimento de usuário do Alto-Falante Inteligente

Os dados do perfil de voz podem ser usados em qualquer reunião com um Alto-Falante Inteligente. Consulte [Políticas de reuniões do Teams](../meetings-policies-recording-and-transcription.md#transcription) e os [cmdlets de reunião do PowerShell](/powershell/module/skype/set-csteamsmeetingpolicy) para obter informações sobre as configurações da reunião.

Os dados do perfil de voz do usuário são criados quando a política é definida para distinguir ou um convidado não-reunião entra durante a reunião. Os dados do perfil de voz são descartados no final da reunião.

A seguir estão as políticas necessárias para definir um alto-falante inteligente e o reconhecimento do usuário.

|Política|Descrição|Valores e Comportamento|
|-|-|-|
|enrollUserOverride|Use para definir a captura de perfil de voz ou o registro nas configurações do Teams para um locatário. |**Desabilitado**<br><ul><li> Os usuários que nunca se inscreveram não podem exibir, registrar ou registrar novamente.<li>O ponto de entrada para o fluxo de registro será oculto.<li>Se os usuários selecionarem um link para a página de registro, verão uma mensagem que afirma que esse recurso não está habilitado para sua organização.  <li>Os usuários registrados podem exibir e remover o perfil de voz nas configurações do Teams. Depois de remover o perfil de voz, eles não poderão exibir, acessar ou concluir o fluxo de registro.</li></ul><br>**Habilitado**<br><ul><li> Os usuários podem exibir, acessar e concluir o fluxo de registro.<li>O ponto de entrada será exibido na página configurações do Teams na guia **Reconhecimento** .</li></ul>|
|roomAttributeUserOverride|Controle a identificação de usuário baseada em voz em salas de reunião. Essa configuração é necessária para contas Salas do Teams.| **Desativado**<br><ul><li>O dispositivo Salas do Teams não enviará largura de banda que salva fluxo de áudio da sala. <li>Os usuários da sala de reunião não serão atribuídos ou distinguidos, e suas assinaturas de voz não serão recuperadas ou usadas.<li>Os usuários da sala de reunião são desconhecidos.</li></ul> <br>**Atributo**<br><ul><li>Os usuários das salas serão atribuídos com base no status de registro.<li>Os usuários registrados são mostrados com o nome na transcrição.  <li>Os usuários que não estão registrados mostram como Orador \<n>.<li>O dispositivo Salas do Teams enviará sete fluxos de áudio da sala.</ul> <br>**Distinguir**<br> <ul><li>Os usuários das salas serão diferenciados e separados como alto-falante 1, alto-falante 2, .... alto-falante \<n> na transcrição.</li><li>Independentemente do status de registro do usuário, seu nome não será exibido na transcrição.</li><li>O dispositivo Salas do Teams enviará sete fluxos de áudio da sala.</li></ul>
|AllowTranscription|Necessário para contas de salas do usuário e do Teams.|**True** e **False**|
||||

No centro de administração do Teams, defina a política **de transcrição** . As configurações estão **desativadas** por padrão.

![o centro de administração com políticas de reunião realçadas e Permitir transcrição selecionada.](../media/allow-transcription1.png)
  
> [!NOTE]
> Depois que uma política é atribuída, ela pode levar até 48 horas para entrar em vigor. Para que a política entre em vigor mais cedo, as contas devem ser assinadas e inseridas novamente.

## <a name="frequently-asked-questions-faq"></a>Perguntas frequentes (FAQ)

**Onde os dados do perfil de voz são armazenados?**

Os dados do perfil de voz são armazenados em Office 365 nuvem com conteúdo do usuário.

**Qual é a linha do tempo de retenção e a política?**

A política de retenção geral é declarada na [visão geral de retenção de dados](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview). Além disso, os dados do perfil de voz de um usuário serão excluídos após um ano se o usuário não for convidado para nenhuma reunião com um Alto-Falante Inteligente nesse período de 1 ano. Os dados não são usados em nenhuma reunião para funcionários existentes. Se um funcionário tiver deixado a empresa, os dados do perfil de voz serão considerados conteúdo do usuário e serão tratados como tal de acordo com Office 365 política de retenção de dados descrita na [visão geral de retenção de dados](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).

**Os dados de perfil de voz são usados em serviços de Microsoft?**

Não, os dados do perfil de voz são usados apenas para a finalidade para a qual o usuário forneceu o consentimento. Microsoft não usará os dados do perfil de voz, exceto nos cenários de reconhecimento de voz do Teams.

Por exemplo, Microsoft não usará os dados nas seguintes situações:

**Meus dados de perfil de voz são usados quando participo de uma reunião em outra organização?**

Não apenas em reuniões organizadas por um usuário em sua organização.

**Como posso exportar meu perfil de voz?**

Seu administrador de TI pode exportar seus dados de áudio a qualquer momento.

## <a name="supported-locales"></a>Localidades com suporte

As seguintes localidades de transcrição de registro e de reunião têm suporte em todos os países e regiões.

### <a name="enrollment-locales"></a>Localidades de registro

Os usuários finais podem registrar suas vozes para reconhecimento nas seguintes localidades:

|**Idioma**|**País/Região**|**ID da cultura**|
|:-----|:-----|:-----|
|Árabe  <br/> |Saudi Arabia (المملكة العربية السعودية) <br/> |ar-SA  <br/> |
|Chinês  <br/> |China <br/> |zh-CN  <br/> |
|Chinês  <br/> |Taiwan <br/> |zh-TW  <br/> |
|Dinamarquês  <br/> |Dinamarca <br/> |da-DK  <br/> |
|Holandês  <br/> |Países Baixos <br/> |nl-NL  <br/> |
|Inglês  <br/> |Austrália <br/> |en-AU  <br/> |
|Inglês  <br/> |Canadá  <br/> |en-CA <br/> |
|Inglês  <br/> |Índia  <br/> |en-IN  <br/> |
|Inglês  <br/> |Nova Zelândia  <br/> |en-NZ  <br/> |
|Inglês  <br/> |Reino Unido  <br/> |en-GB  <br/> |
|Inglês  <br/> |Estados Unidos  <br/> |en-US  <br/> |
|Finlandês  <br/> |Finlândia  <br/> |fi-FI  <br/> |
|Francês  <br/> |Canadá <br/> |fr-CA  <br/> |
|Francês  <br/> |França <br/> |fr-FR  <br/> |
|Italiano  <br/> |Itália <br/> |it-IT  <br/> |
|Japonês  <br/> |Japão <br/> |ja-JP  <br/> |
|Norueguês  <br/> |Noruega <br/> |nb-NO  <br/> |
|Polonês  <br/> |Polônia <br/> |pl-PL  <br/> |
|Português      <br/> |Brasil <br/> |pt-BR  <br/> |
|Russo  <br/> |Rússia <br/> |ru-RU  <br/> |
|Sueco  <br/> |Suécia <br/> |sv-SE  <br/> |
|Espanhol  <br/> |México  <br/> |es-MX  <br/> |
|Espanhol  <br/> |Espanha  <br/> |es-ES  <br/> |

### <a name="in-meeting-transcription-locales"></a>Localidades de transcrição na reunião

Depois que um usuário final se registra, sua voz pode ser reconhecida durante as reuniões e identificada na transcrição quando a reunião é definida como uma das seguintes localidades:

|**Idioma**|**País/Região**|**ID da cultura**|
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

[Artigo de suporte: usar alto-falantes inteligentes para identificar participantes na sala](https://support.microsoft.com/office/use-teams-intelligent-speakers-to-identify-in-room-participants-in-meeting-transcription-a075d6c0-30b3-44b9-b218-556a87fadc00)
