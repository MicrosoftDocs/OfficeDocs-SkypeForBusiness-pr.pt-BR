---
title: Visitas virtuais com Teams - Integração ao Cerner EHR
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
appliesto:
- Microsoft Teams
ms.reviewer: ansantam
description: Saiba como integrar o conector Teams EHR para permitir que os provedores de saúde em sua organização conduzam visitas virtuais com pacientes ou outros provedores em Teams diretamente do sistema cerner EHR.
ms.openlocfilehash: e7d104e4541462c94ddb95805ae7ec2a8619bf5b
ms.sourcegitcommit: 5880de47e986854fca873ae75f76a7ecad194dff
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2022
ms.locfileid: "62763695"
---
# <a name="virtual-visits-with-teams---integration-into-cerner-ehr"></a>Visitas virtuais com Teams - Integração ao Cerner EHR

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

O conector Microsoft Teams EHR (Registro Eletrônico de Saúde) torna mais fácil para os médicos iniciarem uma visita de paciente virtual ou consultarem outro provedor em Microsoft Teams diretamente do sistema cerner EHR. Criado na nuvem Microsoft 365, o Teams permite colaboração e comunicação simples e seguras com chat, vídeo, voz e ferramentas de saúde em um único hub que oferece suporte à conformidade com HIPAA, certificação HITECH e muito mais.

A plataforma de comunicação e colaboração Teams facilita a recortação de sistemas fragmentados pelos médicos, para que eles possam se concentrar em oferecer o melhor cuidado possível. Com o conector Teams EHR, você pode:

- Conduza Teams visitas virtuais do seu sistema cerner EHR com um fluxo de trabalho médico integrado.
- Permitir que os pacientes participem Teams visitas virtuais de notificações por email ou SMS.
- Exibir relatórios de dados de consumo e informações personalizáveis de Qualidade de Chamada para visitas conectadas ao EHR.

Este artigo descreve como configurar e configurar o conector Teams EHR para integrar com a plataforma Cerner. Ele também fornece uma visão geral da experiência de Teams de Visitas Virtuais do sistema Cerner EHR.

## <a name="before-you-begin"></a>Antes de você começar

> [!NOTE]
> Fale com o representante do Cerner e revise seu guia de integração do Cerner antes de habilitar a integração.

### <a name="prerequisites"></a>Pré-requisitos

Antes de integrar o conector Teams EHR em sua organização de saúde, você deve ter o seguinte:

- Uma assinatura ativa para Microsoft Teams de conector EHR autônomo (imposta somente durante o teste em um ambiente de EHR de produção).
- Os usuários têm uma licença Microsoft 365 ou Office 365 que inclui Teams reuniões.
- Teams é adotado e usado em sua organização de saúde.
- Seus sistemas atendem a todos os [requisitos de software e navegador](../../hardware-requirements-for-the-teams-app.md) para Teams.
- Cerner versão Novembro de 2018 ou posterior

## <a name="set-up-the-teams-ehr-connector"></a>Configurar o conector Teams EHR

A configuração do conector requer que você:

- [Iniciar o portal de configuração do conector EHR](#launch-the-ehr-connector-configuration-portal)
- [Insira informações de configuração](#enter-configuration-information)
- [Habilitar notificações SMS (opcional)](#enable-sms-notifications-optional)
- [Análise e conclua a configuração](ehr-admin-cerner.md#review-and-finish-the-configuration)

> [!IMPORTANT]
> Essas etapas devem ser concluídas pelo administrador Microsoft 365 global em sua organização.  

### <a name="launch-the-ehr-connector-configuration-portal"></a>Iniciar o portal de configuração do conector EHR

Para começar, o administrador Microsoft 365 inicia o portal de configuração do conector [EHR](https://ehrconnector.teams.microsoft.com) e faz logo após usar as credenciais da Microsoft.

Seu Microsoft 365 administrador pode configurar um único departamento ou vários departamentos para testar a integração. Configure a URL de teste e produção no portal de configuração. Certifique-se de testar a integração do ambiente de teste cerner antes de ir para a produção.

### <a name="enter-configuration-information"></a>Insira informações de configuração

Em seguida, para configurar a integração, o administrador do Microsoft 365 adiciona uma URL base de Recursos de Interoperabilidade de Saúde Rápida (FHIR) do Cerner e especifica o ambiente. Configure o máximo de URLs base FHIR conforme necessário, dependendo das necessidades da sua organização e dos ambientes que você deseja testar.

:::image type="content" source="media/ehr-admin-cerner-configuration.png" alt-text="Captura de tela da página Informações de configuração do portal Teams de configuração do conector EHR." lightbox="media/ehr-admin-cerner-configuration.png":::

- A URL base FHIR é um endereço estático que corresponde ao ponto de extremidade da API FHIR do servidor. Um exemplo de URL é `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.

- Você pode configurar a integração para ambientes de teste e produção. Para a instalação inicial, recomendamos que você configure o conector de um ambiente de teste antes de ir para a produção.

Depois que a URL base FHIR for validada e o ambiente for selecionado, escolha **Feito**. Em seguida, adicione mais URLs base FHIR para outros ambientes, conforme necessário.

Selecione **Próximo** para ir para a próxima etapa.

### <a name="enable-sms-notifications-optional"></a>Habilitar notificações SMS (opcional)

Conclua esta etapa se sua organização quiser que a Microsoft gerencie notificações SMS para seus pacientes. Quando você habilita as notificações de SMS, seus pacientes receberão mensagens de confirmação e lembrete para visitas agendadas.

Para habilitar notificações sms, o administrador Microsoft 365 faz o seguinte:

1. Na página Notificações por SMS, selecione as duas caixas de seleção de consentimento para:

    - Permita que a Microsoft envie notificações SMS para os pacientes em nome da sua organização.
    - Confirme se você garantirá que os participantes consentiram em enviar e receber mensagens SMS.

    :::image type="content" source="media/ehr-admin-cerner-sms-notifications.png" alt-text="Captura de tela da página notificações sms, mostrando caixas de seleção de consentimento e a opção de gerar um número de telefone." lightbox="media/ehr-admin-cerner-sms-notifications.png":::

1. Em **Seus números de telefone**, selecione **Gerar um novo número de telefone** para gerar um número de telefone para sua organização. Isso inicia o processo para solicitar e gerar um novo número de telefone. Esse processo pode levar até 2 minutos para ser concluído.

    Depois que o número de telefone é gerado, ele é exibido na tela. Esse número será usado para enviar confirmações de SMS e lembretes para seus pacientes. O número foi provisionado, mas ainda não está vinculado à URL base FHIR. Faça isso na próxima etapa.

    :::image type="content" source="media/ehr-admin-cerner-phone-number.png" alt-text="Captura de tela mostrando um exemplo do número de telefone gerado." lightbox="media/ehr-admin-cerner-phone-number.png":::

    Escolha **Feito** e selecione **Próximo**.

1. Para vincular o número de telefone a uma URL base FHIR, **em Telefone na** seção **configuração SMS**, selecione o número. Faça isso para cada URL base FHIR para a qual você deseja habilitar notificações SMS.

    :::image type="content" source="media/ehr-admin-cerner-link-phone-number.png" alt-text="Captura de tela mostrando como vincular um número de telefone a uma URL base FHIR." lightbox="media/ehr-admin-cerner-link-phone-number.png":::

    Se essa for a primeira vez que você estiver configurando o conector, você verá a URL base FHIR inserida na etapa anterior. O mesmo número de telefone pode ser vinculado a várias URLs base FHIR, o que significa que os pacientes receberão notificações SMS do mesmo número de telefone para organizações e/ou departamentos diferentes.

     Selecione **Próximo**.

### <a name="review-and-finish-the-configuration"></a>Análise e conclua a configuração

Você será apresentado com registros de integração para o início do paciente e do provedor. Esses registros são necessários para concluir a configuração de Visitas Virtuais no Cerner. Para obter mais informações, consulte o guia de integração Cerner-Microsoft Teams Telehealth.

> [!NOTE]
> A qualquer momento, o administrador Microsoft 365 pode entrar no portal de configuração para exibir os registros de integração e alterar as configurações, se necessário.

## <a name="launch-teams-virtual-visits"></a>Iniciar Teams virtuais

Depois de concluir as etapas do conector EHR e as etapas de configuração do Cerner, sua organização está pronta para dar suporte a visitas de vídeo com Teams.

### <a name="virtual-visits-prerequisites"></a>Pré-requisitos de Visitas Virtuais

- Seus sistemas devem atender a todos os [requisitos de software e navegador](../../hardware-requirements-for-the-teams-app.md) para Teams.
- Você concluiu a configuração de integração entre a organização cerner e sua Microsoft 365 organização.

### <a name="provider-experience"></a>Experiência do provedor

Os provedores de saúde em sua organização podem participar de visitas usando Teams do portal PowerChart. O provedor deve navegar até o quadro de pacientes onde a opção Teams está disponível.

A partir daí, o provedor pode exibir informações de visita, participar de visitas e enviar o link da reunião. Após a logon única, o provedor é levado diretamente para o compromisso virtual no Teams.

Principais recursos da experiência do provedor:

- Os provedores podem participar de visitas usando navegadores com suporte ou o Teams aplicativo.
- Os provedores podem usar todos os recursos de reunião Teams suporte, incluindo compartilhamento de tela, plano de fundo personalizado e gravação.
- Os provedores podem ver atualizações em tempo real de pacientes que se conectam a uma visita para um determinado compromisso no PowerChart.
- As informações do provedor não são visíveis para os pacientes durante a visita.

> [!NOTE]
> Todas as informações inseridas no chat de reunião necessárias para fins de continuidade ou retenção de registros médicos devem ser baixadas, copiadas e notadas pelo provedor de saúde. O chat não constitui um registro médico legal ou um conjunto de registros designado. As mensagens do chat são armazenadas com base nas configurações criadas pelo Microsoft Teams administrador.

### <a name="patient-experience"></a>Experiência do paciente

O conector dá suporte a pacientes que ingressarem em visitas por meio de um link na mensagem de texto SMS. No momento do compromisso, os pacientes podem iniciar uma visita tocando no link na mensagem de texto SMS.

Principais recursos da experiência do paciente

- Os pacientes podem participar de visitas de navegadores da Web modernos na área de trabalho e em dispositivos móveis sem precisar instalar [o Teams app](../mobile-browser-join.md).
- Os pacientes podem participar de visitas com um único clique e nenhuma outra conta ou login é necessária.
- Os pacientes não são obrigados a criar uma conta da Microsoft ou entrar para iniciar uma visita.
- Os pacientes são colocados em um lobby até que o provedor insusse e os admita.
- Os pacientes podem testar seu vídeo e microfone no lobby antes de ingressar na visita.

## <a name="privacy-and-location-of-data"></a>Privacidade e localização de dados

Teams integração com sistemas EHR otimiza a quantidade de dados usados e armazenados durante a integração e fluxos de Visitas Virtuais. A solução segue os princípios e diretrizes gerais de privacidade e gerenciamento de dados do Teams, descritos em Privacidade do Teams.

O Teams EHR não armazena ou transfere dados pessoais identificáveis ou quaisquer registros de saúde de pacientes ou provedores de saúde do sistema EHR. Os únicos dados que o conector EHR armazena são a ID exclusiva do usuário do EHR, que é usada durante Teams de reunião.

A ID exclusiva do usuário EHR é armazenada em uma das três regiões geográficas descritas em [Onde seus dados de cliente Microsoft 365 são armazenados](/microsoft-365/enterprise/o365-data-locations). Todos os chats, gravações e outros dados compartilhados no Teams por participantes da reunião são armazenados de acordo com as políticas de armazenamento existentes. Para saber mais sobre a localização dos dados Teams, consulte [Local dos dados Teams](../../location-of-data-in-teams.md).

## <a name="related-articles"></a>Artigos relacionados

- [Teams de administrador do conector EHR](ehr-admin-reports.md)
- [Começar a Teams para organizações de saúde](teams-in-hc.md)
