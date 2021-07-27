---
title: Entre em contato com o service desk PSTN
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.pstnservicedesk
- ms.teamsadmincenter.voice.contactPSTNsupport
- Calling Plans
ROBOTS: NOINDEX, NOFOLLOW
description: Quando você receber números de telefone ou números de porta (transferência) para sua organização, talvez seja necessário obter ajuda e suporte no service desk PSTN.
ms.openlocfilehash: b3925fbd473094b06133fb7cfe31479396434b80
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510272"
---
# <a name="pstn-service-desk"></a>PSTN Service Desk 

Há um novo processo para interagir com o service desk PSTN. Agora você pode abrir tíquetes, exibir tíquetes e acompanhar a comunicação em um único local integrado ao Centro de Administração Teams. Este artigo descreve tudo o que você precisa saber para entrar em contato com o service desk.

> [!NOTE]
> A partir de 22 de julho de 2021, o sistema de email atual foi reformado.

Para entrar em contato com o service desk:

1. Faça logoff no Teams Admin Center - admin.teams.microsoft.com.

2. No painel esquerdo, selecione Telefone **números**.

3. Na parte superior da página, selecione **Obter suporte ao número de telefone**. Você verá a Central de Serviços Telefone Número.  

> [!NOTE]
> Somente alguém do mesmo locatário terá permissão para criar um caso. Ou seja, alguém do @fabrikam.com não pode criar um caso em nome do @contoso.com. 

Na Central Telefone de Número, você pode criar novos casos, exibir casos existentes, se comunicar com o service desk e gerenciar seu perfil de usuário. Essas tarefas são descritas em mais detalhes nas seções a seguir.

- **Telefone Central de Serviços de Número**   – Navegue até a home page do Portal. 

- **[Criar um novo caso](#create-a-new-case)**   – Envie uma nova solicitação ou uma consulta geral. 

- **[Exibir meus casos existentes](#view-and-manage-existing-cases)** – Rastrear e monitorar seus casos existentes. 

- **[Exibir casos da minha empresa](#view-and-manage-existing-cases)**   – Acompanhe e monitore os casos existentes da sua empresa. Se seus colegas da sua empresa abrirem quaisquer casos, você poderá procurar por eles neste ponto de vista.  

- **[Comentários](#view-and-manage-existing-cases)**– Compartilhe seus comentários conosco. 

- **[Seu Nome]**   – Atualize sua página de perfil. 


## <a name="create-a-new-case"></a>Criar um novo caso

Para criar um novo caso, siga estas etapas:

1. Selecione **Criar um novo caso** em um dos seguintes locais:  

   - Na página **Telefone Central** de Serviços de Número, na parte superior da página ou no azulejo inferior.

   - Na página **Exibir meus casos existentes.**

   - Na página **Exibir casos da minha** empresa.

2. Forneça os detalhes do caso conforme descrito em detalhes na [próxima seção](#provide-case-details).

3. Depois de inserir todos os valores, selecione **Enviar**. Você verá uma nova tela onde poderá ver seu número de caso.  

### <a name="provide-case-details"></a>Fornecer detalhes de caso

Para entender os detalhes do caso, a Microsoft precisa das seguintes informações:

- [Categoria case](#case-category)
- [País ou região](#country-or-region)
- [Tipo de caso](#case-type)
- [Título de caso](#case-title)
- [Contatos adicionais para notificações](#additional-contacts-for-notifications)
- [Descrição](#description)
- [Documentos de suporte adicionais](#additional-supporting-documents)

#### <a name="case-category"></a>Categoria case

Um caso pode ter uma das duas categorias: 

- **Enviar uma nova solicitação**- Escolha essa opção se quiser enviar uma nova solicitação. Por exemplo, você deseja enviar uma solicitação de porta ou comprar números de telefone da Microsoft.  

- **Consulta geral** - Escolha essa opção se você tiver perguntas que o ajudarão a determinar sua solicitação. Por exemplo, você precisa saber se pode por seus números sem fio para a Microsoft, ou se a Microsoft dá suporte a números de entrada gratuita. 

#### <a name="country-or-region"></a>País ou região

Selecione o país/região para o qual você está enviando esse caso. Se você tiver solicitações para vários países, deverá abrir um caso por país/região.  

#### <a name="case-type"></a>Tipo de caso

O tipo de caso pode ser um dos seguintes:

- **Nome de Chamada Personalizado (Somente EUA)** - De definir um nome de chamada personalizado em seus números de telefone da Microsoft. Isso é aplicável apenas a números de telefone dos Estados Unidos. 

  - **Nome de chamada personalizado para definir (somente 15 caracteres)** - O nome de chamada personalizado que você deseja definir. Name tem um limite máximo de 15 caracteres.  

  - **Lista de números de telefone** - A lista de números de telefone para os quais você deseja definir um valor de nome de chamada personalizado. Upload um arquivo csv com a lista de números de telefone.  

- **Porta de locatário inter** – Mover números de telefone de um locatário para outro. Por exemplo, você tem dois locatários diferentes na Microsoft e deseja mover seus números de telefone de um locatário para o outro.  

  - **Nome de domínio do locatário de** origem - O locatário do qual você deseja mover números de telefone para um locatário diferente.  

  - **Identificador exclusivo do locatário de** origem - A ID do locatário do locatário de origem. Este é um campo opcional.  

  - **Nome de domínio do locatário de** destino - O locatário para o qual você deseja mover números de telefone.  

  - **Identificador exclusivo do locatário de** destino - A ID do locatário para o locatário de destino. Este é um campo opcional.  

  - **Data e hora solicitadas*** - A data e a hora em que você deseja que seus números são movidos do locatário de origem para o locatário de destino. Consulte Data e hora.

  - **Lista de números de telefone** - A lista de números de telefone que você deseja mover do locatário de origem para o locatário de destino. Upload um arquivo csv com a lista de números de telefone. 

- **Alteração de Tipo de** Inventário – Alterar o tipo de número de telefone. Por exemplo, você deseja alterar seus números de assinantes da Microsoft para números de serviço. Para obter mais informações sobre os tipos de números de telefone compatíveis com a Microsoft, consulte [Tipos de números de telefone](../different-kinds-of-phone-numbers-used-for-calling-plans.md).

  - **Converta em** - Selecione para converter seus números em números de usuário ou em números de serviço. 

  - **Data/hora** preferencial * - A data e a hora em que você deseja que o tipo de inventário de seus números seja alterado. Confira Data e hora para obter mais informações.

  - Caixa de seleção – eu sei que para poder atualizar o tipo de inventário, meus números de telefone precisam ser não atribuídos – a Microsoft não pode processar solicitações de alteração de tipo de número de telefone, a menos que os números de telefone em seu locatário não sejam **atribuídos.** Se você estiver solicitando essa alteração para uma data futura, precisará garantir que os números não sejam atribuídos antes da data e hora solicitadas. 

  - **Lista de números de telefone** - A lista de números de telefone cujo tipo você deseja alterar. Upload um arquivo csv com a lista de números de telefone. 

- **Nova Aquisição de TN** – Comprar novos números de telefone da Microsoft.  

  - **Tipo de número** - Selecione o tipo para seus números. Consulte [Tipos de números de telefone](../different-kinds-of-phone-numbers-used-for-calling-plans.md).

  - **Tentou obter** números de telefone do Portal do Centro de Administração do Teams - Você tentou comprar esses números de telefone no portal do Centro de Administração Microsoft Teams, onde você pode fazer o auto-atendimento?  

  - **Quantidade de números de telefone necessários** - A contagem de números de telefone que você deseja comprar.  

  - **Estado/Província** - O estado/província em seu país/região para o qual você deseja números de telefone.  

  - **Cidade** - A cidade dentro do estado/província para a qual você deseja números de telefone.  

  - **Office endereço** - Isso é específico apenas para determinados países. Este é o endereço do site do seu escritório.  

  - **Listagem de diretórios** - Isso é específico apenas para determinados países. Deseja publicar as informações da empresa com os números de telefone?  

- **Port in** – Port existing phone numbers from your current service provider to Microsoft.  

  - **Nomear sua ordem de** porta - Forneça um nome fácil de lembrar para sua solicitação de porta. 

  -  **Data/hora de portabilidade** solicitada * - A data e a hora em que você deseja que os números portam para a Microsoft. Observe que essa não é uma data de portabilidade garantida, pois o proprietário do número atual precisa aprovar nossa solicitação de porta primeiro. Consulte Data e hora. 

  - **Lista de números de portabilidade** - A lista de números de telefone que você gostaria de portar para a Microsoft. Upload um arquivo csv com a lista de números de telefone. 

  - **Carta de autorização (LOA)** - Anexar uma LOA assinada e preenchida aqui. A Microsoft não pode processar uma solicitação de porta sem uma LOA.  

- **Atualização de endereço** – Atualize o endereço de chamada de emergência. Observe que esse campo se aplica somente a países selecionados. 

  - **ID do local** - A ID de local do seu endereço de emergência. 

  - **Lista de números de** telefone - A lista de números de telefone para os quais você deseja alterar o endereço de emergência (insira o endereço desejado no campo Descrição). Upload um arquivo csv com a lista de números de telefone. 

***Data e hora.** Se você selecionar País = França, data = 14/8/2021 e hora = 10h, a solicitação será executada em 14/08/2021 às 10:00. Hora de francês. 

#### <a name="case-title"></a>Título de caso

Insira um título que resume sua pergunta.  

#### <a name="additional-contacts-for-notifications"></a>Contatos adicionais para notificações

Insira a lista de pessoas que receberão notificações de status automatizadas da Microsoft. Por exemplo, você deseja colocar uma ordem de entrada e deseja que outros dois colegas, além de si mesmo, recebam notificações de status automatizadas. Forneça os endereços de email de seus colegas na seção Emails **de** notificação. Essas informações são opcionais. 

#### <a name="description"></a>Descrição

Descreva o que você está tentando obter e listar suas perguntas para o microsoft PSTN Service desk.  

#### <a name="additional-supporting-documents"></a>Documentos de suporte adicionais

Upload documentos adicionais para seu caso.  

## <a name="view-and-manage-existing-cases"></a>Exibir e gerenciar casos existentes

Você pode exibir seus casos selecionando **Exibir meus casos existentes** e selecionando o número da ocorrência. Selecionar um número de caso o redireciona para os detalhes do caso. (Você também pode exibir casos da empresa selecionando **Exibir casos da empresa**.)  Você também pode:

- **Filtre seus casos** selecionando **Casos abertos**, Todos **os casos** ou **Casos Fechados.**

- **Comunique-se** com o service desk PSTN em relação ao seu caso abrindo um caso existente, rolando para baixo e selecionando **Adicionar comentário**. Uma nova janela aparecerá. Insira sua mensagem na caixa de comentários. Anexe quaisquer documentos de suporte (se disponível) que possam ajudar com sua solicitação e selecione **Enviar**.  

  As respostas do service desk PSTN serão exibidas na mesma linha do tempo. Quando houver uma atualização em seu caso, você receberá uma notificação por email automatizada da atualização. 

- **Cancele um caso** navegando para um caso existente, rolando para baixo e selecionando **Cancelar caso.** Selecione um motivo para o cancelamento na listada e selecione **Cancelar**.  

- **Resolver um caso** - Se você acredita que sua solicitação foi concluída, você pode resolver um caso navegando para um caso existente, rolando para baixo e selecionando **Resolver caso**. Selecione **Fechar;** o caso agora será como **Resolvido – Problema resolvido.**  


## <a name="related-topics-and-additional-resources"></a>Tópicos relacionados e recursos adicionais

- Para assistência relacionada à configuração e configuração de números, licenças, taxas ou cobranças, consulte [Support Contact for Business Products - Admin Help](/microsoft-365/admin/contact-support-for-business-products?tabs=online&view=o365-worldwide).

- Para obter informações sobre os planos de chamada que estão disponíveis em seu país/região, consulte Disponibilidade de países e região para [Audioconferência e Planos de Chamada.](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

- Para obter informações que podem ajudá-lo a selecionar os tipos apropriados de números de telefone para sua organização, consulte [Diferentes tipos de números de telefone](../different-kinds-of-phone-numbers-used-for-calling-plans.md).

- Para obter informações sobre como gerenciar números de telefone para sua organização, consulte [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization.md).

- Para obter informações sobre condições e termos de chamada de emergência, consulte Termos e condições de chamada [de emergência.](../emergency-calling-terms-and-conditions.md)
