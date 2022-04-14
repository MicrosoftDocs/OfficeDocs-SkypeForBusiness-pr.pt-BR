---
title: Visitas virtuais com Teams – Integração ao Cerner EHR
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
description: Saiba como integrar o conector Teams EHR para permitir que os provedores de serviços de saúde em sua organização realizem Visitas Virtuais com pacientes ou outros provedores no Teams diretamente do sistema Cerner EHR.
ms.openlocfilehash: b5a5a860036b3b561d5a6e18a13b71e072998aa4
ms.sourcegitcommit: 480046a53dfb6e6cf867e1920f8fb43dda9d3774
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2022
ms.locfileid: "64703687"
---
# <a name="virtual-visits-with-teams---integration-into-cerner-ehr"></a>Visitas virtuais com Teams – Integração ao Cerner EHR

O conector Microsoft Teams EHR (Registro Eletrônico de Saúde) facilita a inicialização de uma visita de paciente virtual ou consulta com outro provedor no Microsoft Teams diretamente do sistema Cerner EHR. Criado na nuvem Microsoft 365, o Teams permite colaboração e comunicação simples e seguras com ferramentas de chat, vídeo, voz e serviços de saúde em um único hub que dá suporte à conformidade com HIPAA, certificação HITECH e muito mais.

A plataforma de comunicação e colaboração Teams torna mais fácil para os médicos cortarem a confusão de sistemas fragmentados para que possam se concentrar em fornecer o melhor atendimento possível. Com o Teams EHR, você pode:

- Realize Teams Visitas Virtuais do seu sistema Cerner EHR com um fluxo de trabalho clínico integrado.
- Permitir que os pacientes ingressem Teams visitas virtuais por email ou notificações por SMS.
- Exiba relatórios de dados de consumo e informações personalizáveis de Qualidade de Chamadas para visitas conectadas ao EHR.

Este artigo descreve como configurar o conector Teams EHR para integração com a plataforma Cerner. Ele também fornece uma visão geral da experiência Teams visitas virtuais do sistema Cerner EHR.

## <a name="before-you-begin"></a>Antes de você começar

> [!NOTE]
> Certifique-se de falar com seu representante do Cerner e examinar o guia de integração do Cerner antes de habilitar a integração.

### <a name="prerequisites"></a>Pré-requisitos

Antes de integrar o Teams EHR em sua organização de saúde, você deve ter o seguinte:

- Uma assinatura ativa para Microsoft Teams oferta autônoma do conector EHR (imposta somente durante o teste em um ambiente de EHR de produção).
- Os usuários têm uma licença Microsoft 365 ou Office 365 que inclui Teams reuniões.
- Teams é adotado e usado em sua organização de saúde.
- Seus sistemas atendem a todos os [requisitos de software e navegador](../../hardware-requirements-for-the-teams-app.md) para Teams.
- Cerner versão novembro de 2018 ou posterior

## <a name="set-up-the-teams-ehr-connector"></a>Configurar o conector Teams EHR

A configuração do conector requer que você:

- [Iniciar o portal de configuração do conector EHR](#launch-the-ehr-connector-configuration-portal)
- [Inserir informações de configuração](#enter-configuration-information)
- [Habilitar notificações por SMS (opcional)](#enable-sms-notifications-optional)
- [Análise e conclua a configuração](ehr-admin-cerner.md#review-and-finish-the-configuration)

> [!IMPORTANT]
> Essas etapas devem ser concluídas pelo Microsoft 365 administrador global em sua organização.  

### <a name="launch-the-ehr-connector-configuration-portal"></a>Iniciar o portal de configuração do conector EHR

Para começar, o administrador do Microsoft 365 inicia o portal de configuração do conector [EHR](https://ehrconnector.teams.microsoft.com) e entra usando suas credenciais da Microsoft.

Seu Microsoft 365 administrador pode configurar um único departamento ou vários departamentos para testar a integração. Configure a URL de teste e produção no portal de configuração. Certifique-se de testar a integração do ambiente de teste do Cerner antes de passar para a produção.

### <a name="enter-configuration-information"></a>Inserir informações de configuração

Em seguida, para configurar a integração, o administrador do Microsoft 365 adiciona uma URL base do FHIR (Fast Health Interoperability Resources) do Cerner e especifica o ambiente. Configure quantas URLs base do FHIR forem necessárias, dependendo das necessidades da sua organização e dos ambientes que você deseja testar.

:::image type="content" source="media/ehr-admin-cerner-configuration.png" alt-text="Captura de tela da página Informações de configuração do portal Teams de configuração do conector EHR." lightbox="media/ehr-admin-cerner-configuration.png":::

- A URL base do FHIR é um endereço estático que corresponde ao ponto de extremidade da API FHIR do servidor. Um exemplo de URL é `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.

- Você pode configurar a integração para ambientes de teste e produção. Para a configuração inicial, incentivamos você a configurar o conector de um ambiente de teste antes de passar para a produção.

Depois que a URL base do FHIR for validada e o ambiente estiver selecionado, escolha **Concluído**. Em seguida, adicione mais URLs base FHIR para outros ambientes, conforme necessário.

Selecione **Avançar** para ir para a próxima etapa.

### <a name="enable-sms-notifications-optional"></a>Habilitar notificações por SMS (opcional)

Conclua esta etapa se sua organização quiser que a Microsoft gerencie notificações por SMS para seus pacientes. Quando você habilita as notificações por SMS, seus pacientes receberão mensagens de confirmação e lembrete para visitas agendadas.

Para habilitar as notificações por SMS, Microsoft 365 administrador do Microsoft 365 faz o seguinte:

1. Na página de notificações por SMS, marque as duas caixas de seleção de consentimento para:

    - Permita que a Microsoft envie notificações por SMS para pacientes em nome de sua organização.
    - Confirme que você garantirá que os participantes consentirem em enviar e receber mensagens SMS.

    :::image type="content" source="media/ehr-admin-cerner-sms-notifications.png" alt-text="Captura de tela da página de notificações por SMS, mostrando as caixas de seleção de consentimento e a opção de gerar um número de telefone." lightbox="media/ehr-admin-cerner-sms-notifications.png":::

1. Em **Seus números de telefone**, selecione **Gerar um novo número de telefone** para gerar um número de telefone para sua organização. Isso inicia o processo para solicitar e gerar um novo número de telefone. Esse processo pode levar até 2 minutos para ser concluído.

    Depois que o número de telefone é gerado, ele é exibido na tela. Esse número será usado para enviar confirmações por SMS e lembretes para seus pacientes. O número foi provisionado, mas ainda não está vinculado à URL base do FHIR. Faça isso na próxima etapa.

    :::image type="content" source="media/ehr-admin-cerner-phone-number.png" alt-text="Captura de tela mostrando um exemplo do número de telefone gerado." lightbox="media/ehr-admin-cerner-phone-number.png":::

    Escolha **Concluído** e, em seguida, **selecione Avançar**.

1. Para vincular o número de telefone a uma URL base do FHIR, em Telefone **na** seção de configuração **de SMS**, selecione o número. Faça isso para cada URL base do FHIR para a qual você deseja habilitar notificações por SMS.

    :::image type="content" source="media/ehr-admin-cerner-link-phone-number.png" alt-text="Captura de tela mostrando como vincular um número de telefone a uma URL base do FHIR." lightbox="media/ehr-admin-cerner-link-phone-number.png":::

    Se esta for a primeira vez que você está configurando o conector, você verá a URL base do FHIR que foi inserida na etapa anterior. O mesmo número de telefone pode ser vinculado a várias URLs base do FHIR, o que significa que os pacientes receberão notificações por SMS do mesmo número de telefone para organizações e/ou departamentos diferentes.

     Selecione **Avançar**.

### <a name="review-and-finish-the-configuration"></a>Análise e conclua a configuração

Você verá registros de integração para inicialização de pacientes e provedores. Esses registros são necessários para concluir a configuração de Visitas Virtuais no Cerner. Para obter mais informações, consulte o guia Cerner-Microsoft Teams Integração de Telehealth.

> [!NOTE]
> A qualquer momento, o Microsoft 365 administrador pode entrar no portal de configuração para exibir registros de integração e alterar as definições de configuração, se necessário.

## <a name="launch-teams-virtual-visits"></a>Iniciar Teams virtuais

Depois de concluir as etapas do conector EHR e as etapas de configuração do Cerner, sua organização estará pronta para dar suporte a visitas em vídeo com Teams.

### <a name="virtual-visits-prerequisites"></a>Pré-requisitos de Visitas Virtuais

- Seus sistemas devem atender a todos os [requisitos de software e navegador](../../hardware-requirements-for-the-teams-app.md) para Teams.
- Você concluiu a configuração de integração entre a organização cerner e sua Microsoft 365 organização.

### <a name="provider-experience"></a>Experiência do provedor

Os provedores de serviços de saúde em sua organização podem ingressar em visitas usando Teams portal do PowerChart. O provedor deve navegar até o quadro de pacientes em que Teams opção está disponível.

A partir daí, o provedor pode exibir informações de visita, ingressar em visitas e enviar o link da reunião. Após a entrada única, o provedor é levado diretamente para o compromisso virtual em Teams.

Principais recursos da experiência do provedor:

- Os provedores podem ingressar em visitas usando navegadores com suporte ou o Teams aplicativo.
- Os provedores podem usar todos os recursos de reunião Teams suporte, incluindo compartilhamento de tela, tela de fundo personalizada e gravação.
- Os provedores podem ver atualizações em tempo real de pacientes que se conectam a uma visita para um determinado compromisso no PowerChart.
- As informações do provedor não são visíveis para os pacientes durante a visita.

> [!NOTE]
> Todas as informações inseridas no chat de reunião necessárias para fins de continuidade ou retenção de registros médicos devem ser baixadas, copiadas e anotadas pelo provedor de serviços de saúde. O chat não constitui um registro médico legal ou um conjunto de registros designado. As mensagens do chat são armazenadas com base nas configurações criadas pelo Microsoft Teams administrador.

### <a name="patient-experience"></a>Experiência do paciente

O conector dá suporte a pacientes que ingressam em visitas por meio de um link na mensagem de texto SMS. No momento da consulta, os pacientes podem iniciar uma visita tocando no link na mensagem de texto SMS.

Principais recursos da experiência do paciente

- Os pacientes podem ingressar em visitas de [navegadores da Web modernos na área](../browser-join.md) de trabalho e em dispositivos móveis sem precisar instalar o Teams aplicativo.
- Os pacientes podem ingressar em visitas com um único clique e nenhuma outra conta ou entrada é necessária.
- Os pacientes não precisam criar uma conta da Microsoft ou entrar para iniciar uma visita.
- Os pacientes são colocados em um lobby até que o provedor ingresse e os admita.
- Os pacientes podem testar o vídeo e o microfone no lobby antes de ingressar na visita.

## <a name="get-insight-into-virtual-visits-usage"></a>Obter informações sobre o uso de Visitas Virtuais

O [relatório de uso de](../../teams-analytics-and-reports/virtual-visits-usage-report.md) Visitas Virtuais no centro Microsoft Teams administradores fornece aos administradores uma visão geral Teams atividades de Visitas Virtuais em sua organização. O relatório mostra análises detalhadas para compromissos virtuais, incluindo Teams reuniões integradas ao EHR realizadas do sistema EHR.

Você pode exibir as principais métricas, como o tempo de espera do lobby e a duração da visita. Use essas informações para obter informações sobre tendências de uso para ajudá-lo a otimizar as Visitas Virtuais para fornecer melhores resultados de negócios.

## <a name="privacy-and-location-of-data"></a>Privacidade e localização de dados

Teams integração com sistemas EHR otimiza a quantidade de dados usados e armazenados durante a integração e os fluxos de Visitas Virtuais. A solução segue os princípios e diretrizes gerais de privacidade e gerenciamento de dados do Teams, descritos em Privacidade do Teams.

O Teams EHR não armazena nem transfere dados pessoais identificáveis ou quaisquer registros de saúde de pacientes ou provedores de serviços de saúde do sistema EHR. Os únicos dados que o conector EHR armazena são a ID exclusiva do usuário do EHR, que é usada durante Teams de reunião.

A ID exclusiva do usuário EHR é armazenada em uma das três regiões geográficas descritas em [Onde seus dados de cliente Microsoft 365 são armazenados](/microsoft-365/enterprise/o365-data-locations). Todos os chats, gravações e outros dados compartilhados Teams por participantes da reunião são armazenados de acordo com as políticas de armazenamento existentes. Para saber mais sobre a localização dos dados Teams, consulte [Local dos dados Teams](../../location-of-data-in-teams.md).

## <a name="related-articles"></a>Artigos relacionados

- [Teams de uso de Visitas Virtuais](../../teams-analytics-and-reports/virtual-visits-usage-report.md)
- [Teams de administração do conector EHR](ehr-admin-reports.md)
- [Introdução com o Teams para organizações de saúde](teams-in-hc.md)
