---
title: Entre em contato com a equipe dos Serviços de Números de Telefone
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.tnsservicedesk
- ms.teamsadmincenter.voice.contacttnssupport
- Calling Plans
ROBOTS: NOINDEX, NOFOLLOW
description: Quando você obtém números de telefone ou porta (transferência) para sua organização, talvez seja necessário obter ajuda e suporte no service desk do TNS.
ms.openlocfilehash: 9984775a05458592fe1789c0dd8b173a08783220
ms.sourcegitcommit: fd56fb16ed60b027d3f8de96711d143825f9c184
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/20/2023
ms.locfileid: "69835554"
---
# <a name="telephone-number-services-tns---service-desk"></a>TNS (Serviços de Número de Telefone) – Service Desk

> [!NOTE]
> A partir de 22 de julho de 2021, o sistema de email anterior para entrar em contato com o service desk do TNS foi desativado.

Há um novo processo para interagir com o service desk do TNS (Serviços de Número de Telefone) da nossa nova **[Central de Serviços de Número de Telefone](https://pstnsd.powerappsportals.com)**. Agora você pode abrir os tickets, visualizar os tickets e rastrear a comunicação em um único local integrado ao Centro de Administração do Teams. Essas tarefas estão descritas com mais detalhes nas seções a seguir.


- **[Criar um novo caso](#create-a-new-case)** – enviar uma nova solicitação ou inquérito geral.

- **[Exibir meus casos existentes](#view-and-manage-existing-cases)** – acompanhe e monitore seus casos existentes.

- **[Exibir casos da minha empresa](#view-and-manage-existing-cases)** – acompanhe e monitore os casos existentes da sua empresa. Se seu colegas de empresa abriram ocorrências, você pode procurá-las nesta exibição.

- **[Dê comentários](#view-and-manage-existing-cases)**: compartilhe seus comentários conosco.

## <a name="create-a-new-case"></a>Criar uma nova ocorrência

> [!NOTE]
> Somente alguém do mesmo locatário pode criar um caso. Por exemplo, alguém de @fabrikam.com não pode criar um caso em nome de @contoso.com.

Para criar um novo caso, siga estas etapas:

1. Selecione **Criar uma nova ocorrência** a partir de um dos seguintes locais:

   - Na página inicial da **Central de Serviço de Número de Telefone** , na parte superior da página ou no bloco inferior.

   - A partir da  página **Exibir minhas ocorrências existentes**.

   - A partir da  página **Exibir as ocorrências da minha empresa**.

2. Forneça os detalhes da sua ocorrência conforme descrito detalhadamente na [próxima seção](#provide-case-details).

3. Depois de inserir todos os valores, selecione **Enviar**. Você verá uma nova tela em que poderá ver o número do caso.

### <a name="provide-case-details"></a>Forneça detalhes da ocorrência

Para entender os detalhes da ocorrência, a Microsoft precisará das seguintes informações:

- [Categoria da ocorrência](#case-category)
- [País ou região](#country-or-region)
- [Tipo da ocorrência](#case-type)
- [Título da ocorrência](#case-title)
- [Contatos adicionais para notificações](#additional-contacts-for-notifications)
- [Descrição](#description)
- [Documentos de suporte adicionais](#additional-supporting-documents)

#### <a name="case-category"></a>Categoria da ocorrência

Uma ocorrência pode ter uma de duas categorias:

- **Enviar uma nova solicitação** - Escolha esta opção se desejar enviar uma nova solicitação. Por exemplo, você deseja enviar uma solicitação de portabilidade ou comprar números de telefone da Microsoft.

- **Inquérito geral** – escolha essa opção se você tiver perguntas que ajudarão você a determinar sua solicitação. Por exemplo, você precisa saber se pode fazer a portabilidade de seus números sem fio para a Microsoft ou se a Microsoft oferece suporte para números gratuitos personalizados.

#### <a name="country-or-region"></a>País ou região

Selecione o país/região para o qual você está enviando esta ocorrência. Se você tiver solicitações para vários países/regiões, deve abrir uma ocorrência por país/região.

#### <a name="case-type"></a>Tipo de ocorrência

O tipo de ocorrência pode ser um dos seguintes:

- **Nome de Chamada Personalizado (Apenas nos EUA)** - Defina um nome de chamada personalizado em seus números de telefone da Microsoft. Isso se aplica apenas aos números de telefone dos Estados Unidos.

  - **Nome de chamada personalizado a ser definido (apenas 15 caracteres)** - O nome de chamada personalizado que você deseja definir. O nome tem um limite máximo de 15 caracteres.

  - **Lista de números de telefone** - A lista de números de telefone para os quais você deseja definir um valor de nome de chamada personalizado. Faça upload de um arquivo CSV com a lista de números de telefone.

- **Portabilidade entre locatário** - Mova os números de telefone de um locatário para outro. Por exemplo, você tem dois locatários diferentes na Microsoft e deseja mover seus números de telefone de um locatário para outro.

  - **Nome de domínio do locatário de origem** - O locatário do qual você deseja mover os números de telefone para um locatário diferente.

  - **Identificador exclusivo do locatário de origem** - A ID do locatário para o locatário de origem. Este é um campo opcional.

  - **Nome de domínio do locatário de destino** - O locatário para o qual você deseja mover os números de telefone.

  - **Identificador exclusivo do locatário de destino** - A ID do locatário para o locatário de destino. Este é um campo opcional.

  - **Data e hora Solicitada** * - A data e a hora em que você deseja que seus números sejam movidos do locatário de origem para o locatário de destino. Consulte a Data e a Hora.

  - **Lista de números de telefone** - A lista de números de telefone que você deseja mover do locatário de origem para o locatário de destino. Faça upload de um arquivo CSV com a lista de números de telefone.

- **Alteração do Tipo de Inventário** - Altere o tipo de número(s) de telefone. Por exemplo, você deseja alterar seus números de assinante da Microsoft para números de serviço. Para obter mais informações sobre os tipos de números de telefone suportados pela Microsoft, consulte [Tipos de números de telefone](../different-kinds-of-phone-numbers-used-for-calling-plans.md).

  - **Converter para** - Selecione para converter seus números em números de usuário ou de serviço.

  - **Data e hora Preferencial** * - A data e a hora em que você deseja que o tipo de inventário dos seus números seja alterado. Consulte a Data e a hora para obter mais informações.

  - **Caixa de seleção – Entendo que para poder atualizar o tipo de inventário, meus números de telefone precisam ser não atribuídos** – a Microsoft não pode processar solicitações de alteração de tipo de número de telefone, a menos que os números de telefone dentro do locatário não sejam atribuídos. Se estiver solicitando essa alteração para uma data futura, você precisará garantir que os números não serão atribuídos antes da data e hora solicitadas.

  - **Lista de números de telefone** - A lista de números de telefone cujo tipo você deseja alterar. Faça upload de um arquivo CSV com a lista de números de telefone.

- **Nova Aquisição de NT** - Compre novos números de telefone da Microsoft.

  - **Tipo de número** - Selecione o tipo dos seus números. Consulte [Tipos de números de telefone](../different-kinds-of-phone-numbers-used-for-calling-plans.md).

  - **Tentou obter números de telefone do Portal do Teams Administração Center** - Você já tentou comprar esses números de telefone do Centro de Administração do Microsoft Teams?

  - **Quantidade de números de telefone necessária** - A contagem de números de telefone que você deseja comprar.

  - **Estado/Província** - O estado/província no seu país/região para o qual você deseja os números de telefone.

  - **Cidade** - A cidade dentro do estado/província para a qual você deseja os números de telefone.

  - **Endereço comercial** - Isso é específico apenas para alguns países/regiões. Este é o endereço do site do seu escritório.

  - **Lista do diretório** - Isso é específico apenas para alguns países/regiões. Quer publicar as informações da sua empresa com os números de telefone?

- **Portabilidade** - Faça a portabilidade de seus números de telefone existentes do seu provedor de serviços atual para a Microsoft.

  - **Nomear seu pedido de portabilidade** - Forneça um nome fácil de lembrar para seu pedido de portabilidade.

  - **Data/hora da portabilidade solicitada** * - A data e a hora em que você deseja que seja feita a portabilidade dos números para a Microsoft. Essa não é uma data de portabilidade garantida porque o proprietário do número atual precisa aprovar nossa solicitação de porta primeiro. Consulte a Data e a Hora.

  - **Lista de números de portabilidade** - A lista de números de telefone que você deseja fazer a portabilidade para a Microsoft. Faça upload de um arquivo CSV com a lista de números de telefone.

  - **Carta de autorização (LOA)** - Anexe uma LOA assinada e preenchida aqui. A Microsoft não pode processar uma solicitação de portabilidade sem uma LOA.

    > [!NOTE]
    > Para obter mais informações sobre LOAs para portar/transferir números de telefone existentes e requisitos adicionais de documentação, consulte [Gerenciar números de telefone para Plano de Chamada](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).
    >
    >Para portar/transferir 999 ou menos números de telefone para seus usuários, carregue os LOAs concluídos e assinados no centro de administração do Microsoft Teams para processamento adicional.
    >
    > Para portar/transferir mais de 999 números de telefone ou se você tiver problemas com o processo de portabilidade no centro de administração do Microsoft Teams, você poderá [enviar manualmente um pedido de porta](/microsoftteams/phone-number-calling-plans/manually-submit-port-order) para o Service Desk do TNS para sua região.

- **Atualização de Endereço** - Atualize o endereço da chamada de emergência. Observe que este campo se aplica apenas a alguns países/regiões.

  - **ID do local** - A ID do local do seu endereço de emergência.

  - **Lista de números de telefone** - A lista de números de telefone para os quais você deseja alterar o endereço de emergência (insira o endereço desejado no campo Descrição). Faça upload de um arquivo CSV com a lista de números de telefone.

**Data e Hora.** Se você selecionar País = França, data = 14/8/2021 e hora = 10h, a solicitação será executada em 14/8/2021 às 10h Horário francês.

#### <a name="case-title"></a>Título da ocorrência

Insira um título que resuma sua pergunta.

#### <a name="additional-contacts-for-notifications"></a>Contatos adicionais para notificações

Insira a lista de pessoas que receberão as notificações de status automatizadas da Microsoft.
Por exemplo, você deseja colocar uma ordem de portabilidade e deseja que dois outros colegas, além de você, recebam as notificações de status automatizadas. Forneça os endereços de email de seus colegas na seção **Emails de notificação**. Esta informação é opcional.

#### <a name="description"></a>Descrição

Descreva o que você está tentando alcançar e liste suas perguntas para o serviço TNS (Serviço de Número de Telefone) da Microsoft.

#### <a name="additional-supporting-documents"></a>Documentos de apoio adicionais

Faça upload de quaisquer documentos adicionais para sua ocorrência.

## <a name="view-and-manage-existing-cases"></a>Exibir e gerenciar ocorrências existentes

Você pode exibir suas ocorrências selecionando **Exibir minhas ocorrências existentes** e selecionando o número da ocorrência. Selecionar o número da ocorrência o redirecionará para os detalhes da ocorrência. (Você também pode visualizar ocorrências de empresas selecionando **Exibir ocorrências de empresas**.) Você também pode:

- **Filtre suas ocorrências** selecionando **Ocorrências abertas**,  **Todas as ocorrências** ou **Ocorrências fechadas**.

- **Comunique-se com o service desk TNS** em relação ao seu caso abrindo um caso existente, rolando para baixo e selecionando **Adicionar comentário**. Uma nova janela aparecerá. Digite sua mensagem na caixa de comentários. Anexe todos os documentos de suporte (se disponível) e selecione **Enviar**.

  As respostas do **service desk TNS** serão exibidas na mesma linha do tempo. Quando houver uma atualização da sua ocorrência, você receberá uma notificação automática por email sobre a atualização.

- **Cancele uma ocorrência** navegando até uma ocorrência existente, rolando para baixo e selecionando **Cancelar ocorrência.** Selecione um motivo para o cancelamento na lista suspensa e selecione **Cancelar**.

- **Resolver uma ocorrência** Se você acredita que sua solicitação foi concluída, você pode resolver uma ocorrência navegando até uma ocorrência existente, rolando para baixo e selecionando **Resolver ocorrência**. Selecione **Fechar**; a ocorrência agora será mostrada como **Resolvido - Problema resolvido**.

## <a name="related-topics-and-additional-resources"></a>Tópicos relacionados e recursos adicionais

- Para obter assistência relacionada à instalação e configuração de números, licenças, taxas ou cobrança, consulte [Contatar o Suporte para Produtos de uso Empresarial - Ajuda para Administradores](/microsoft-365/admin/contact-support-for-business-products?tabs=online).

- Para obter informações sobre os planos de chamadas disponíveis no seu país/região, consulte [Disponibilidade de países e regiões para audioconferência e planos de chamadas](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).

- Para obter informações sobre os tipos apropriados de números de telefone para sua organização, consulte [Diferentes tipos de números de telefone](../different-kinds-of-phone-numbers-used-for-calling-plans.md).

- Para obter informações sobre como gerenciar números de telefone para sua organização, consulte [Gerenciar números de telefone para sua organização](manage-phone-numbers-for-your-organization.md).

- Para obter informações sobre os termos e condições de chamadas de emergência, consulte [Termos e condições de chamadas de emergência](../emergency-calling-terms-and-conditions.md).
