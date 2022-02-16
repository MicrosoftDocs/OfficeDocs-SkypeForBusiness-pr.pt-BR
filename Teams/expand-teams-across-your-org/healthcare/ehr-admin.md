---
title: Visitas virtuais com Teams - Integração ao EHR Épico
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
description: Saiba como integrar o conector Teams EHR para permitir que os provedores de saúde em sua organização conduzam visitas virtuais com pacientes ou outros provedores em Teams diretamente do sistema EHR épico.
ms.openlocfilehash: 3274ed2c566008dd7474accf159540c96c82b865
ms.sourcegitcommit: 5880de47e986854fca873ae75f76a7ecad194dff
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2022
ms.locfileid: "62763316"
---
# <a name="virtual-visits-with-teams---integration-into-epic-ehr"></a>Visitas virtuais com Teams - Integração ao EHR Épico

O conector Microsoft Teams EHR (Registro Eletrônico de Saúde) torna mais fácil para os médicos iniciarem uma visita de paciente virtual ou consulta com outro provedor em Microsoft Teams diretamente do sistema EHR épico. Criado na nuvem Microsoft 365, o Teams permite colaboração e comunicação simples e seguras com chat, vídeo, voz e ferramentas de saúde em um único hub que oferece suporte à conformidade com HIPAA, certificação HITECH e muito mais.

A plataforma de comunicação e colaboração Teams facilita a recortação de sistemas fragmentados pelos médicos, para que eles possam se concentrar em oferecer o melhor cuidado possível. Com o conector Teams EHR, você pode:

- Iniciar Teams visitas virtuais do seu sistema EHR épico com um fluxo de trabalho médico integrado.
- Permitir que os pacientes participem Teams visitas virtuais de dentro do portal do paciente ou por SMS.
- Suporte a outros cenários, incluindo vários participantes, visitas em grupo e serviços de intérprete.
- Escreva metadados de volta ao sistema EHR Teams as Visitas Virtuais para gravar quando os participantes se conectarem, se desconectarem e habilitarem a auditoria automática e a manutenção de registros.
- Exibir relatórios de dados de consumo e informações personalizáveis de Qualidade de Chamada para visitas conectadas ao EHR.

Confira este vídeo para ver uma visão geral de como gerenciar as Visitas Virtuais no portal do EHR.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

Este artigo descreve como configurar e configurar o conector Teams EHR para se integrar à plataforma Épico em sua organização de saúde. Ele também fornece uma visão geral da experiência de Teams de Visitas Virtuais do sistema EHR épico.

## <a name="before-you-begin"></a>Antes de você começar

Antes de começar, há algumas coisas a fazer para se preparar para a integração.

### <a name="get-familiar-with-the-integration-process"></a>Familiarizar-se com o processo de integração

Revise as informações a seguir para obter uma compreensão do processo de integração geral.

:::image type="content" source="media/ehr-connector-epic-flow.png" alt-text="Imagem resumindo as etapas do processo de integração geral.":::

||||||
|---------|---------|---------|---------|---------|
|**Ação**: você [solicita acesso ao Teams aplicativo](#request-access-to-the-teams-app). <br> **Resultado**: autorizamos sua organização para testes.|**Ação**: criamos um certificado de chave pública e privada e os carregamos na Epic. <br> **Resultado**: a Épico sincroniza o certificado de chave pública.|**Ação**: conclua as etapas de configuração no portal de configuração do conector EHR. <br> **Resultado**: você recebe registros FDI para configuração épica.| **Ação**: você trabalha com seu especialista técnico da Épico para configurar registros FDI na Épico.<br> **Resultado**: Configuração concluída. Pronto para teste.|**Ação**: você conclui o teste em seu ambiente de teste.<br> **Resultado**: validação completa de fluxos e decisão de migrar para produção.|

### <a name="request-access-to-the-teams-app"></a>Solicitar acesso ao aplicativo Teams aplicativo

Você precisará solicitar acesso ao aplicativo Teams.

1. Solicite o download do Teams aplicativo no marketplace [do Pomar de Aplicativos Épicos](https://apporchard.epic.com/Gallery?id=6153). Isso aciona uma solicitação da Épico para a equipe de conectores do Microsoft EHR.
1. Depois de fazer sua solicitação, envie um email [](mailto:teamsforhealthcare@service.microsoft.com) para TeamsForHealthcare@service.microsoft.com com o nome da sua organização, a ID do locatário e o endereço de email do seu contato técnico da Épico.
1. A equipe do conector do Microsoft EHR responderá ao seu email com a confirmação da habilitação.

### <a name="review-the-epic-microsoft-teams-telehealth-integration-guide"></a>Revise o guia Epic-Microsoft Teams Integração de Telehealth

Consulte o [Guia de integração de Telessaúde do Epic-Microsoft Teams](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357) com o especialista técnico do seu Epic. Certifique-se de que todos os pré-requisitos sejam atendidos.

## <a name="prerequisites"></a>Pré-requisitos

- Uma assinatura ativa para Microsoft Cloud para Serviços de Saúde ou uma assinatura para uma oferta autônoma do conector EHR Microsoft Teams EHR (imposta somente ao testar em um ambiente de EHR de produção).
- Versão épica novembro de 2018 ou posterior.
- Os usuários têm uma licença Microsoft 365 ou Office 365 que inclui Teams reuniões.
- Teams é adotado e usado em sua organização de saúde.
- Seus sistemas atendem a todos os [requisitos de software e navegador](../../hardware-requirements-for-the-teams-app.md) para Teams.

> [!IMPORTANT]
> Certifique-se de concluir as etapas de pré-integração e todos os pré-requisitos são atendidos antes de avançar com a integração.

As etapas de integração são executadas pelas seguintes pessoas em sua organização:

- **Microsoft 365 administrador global**: a principal pessoa responsável pela integração. O administrador configura o conector, habilita o SMS (se necessário) e adiciona o analista de clientes épico que aprovará a configuração.
- **Analista de cliente épico**: uma pessoa em sua organização que tem credenciais de logon para a Epic. Eles aprovam as configurações inseridas pelo administrador e fornecem os registros de configuração para a Epic.

O Microsoft 365 administrador e o analista de cliente épico podem ser a mesma pessoa.

## <a name="set-up-the-teams-ehr-connector"></a>Configurar o conector Teams EHR

A configuração do conector requer que você:

- [Iniciar o portal de configuração do conector EHR](#launch-the-ehr-connector-configuration-portal)
- [Insira informações de configuração](#enter-configuration-information)
- [Habilitar notificações SMS (opcional)](#enable-sms-notifications-optional)
- [Aprovar ou exibir a configuração](#approve-or-view-the-configuration)
- [Análise e conclua a configuração](#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>Iniciar o portal de configuração do conector EHR

Para começar, o administrador do Microsoft 365 inicia o portal de configuração do conector [EHR](https://ehrconnector.teams.microsoft.com) e faz login usando suas credenciais Microsoft 365 de usuário.

Seu Microsoft 365 administrador pode configurar uma única organização ou várias organizações para testar a integração. Configure a URL de teste e produção no portal de configuração. Certifique-se de testar a integração do ambiente de teste da Épico antes de ir para a produção.

> [!NOTE]
> Seu Microsoft 365 administrador e analista de clientes épico devem concluir as etapas de integração no portal de configuração. Para etapas de configuração épica, entre em contato com o especialista técnico da Épico atribuído à sua organização.

### <a name="enter-configuration-information"></a>Insira informações de configuração

Em seguida, para configurar a integração, o administrador Microsoft 365 faz o seguinte:

1. Adiciona uma URL base de Recursos de Interoperabilidade de Saúde Rápida (FHIR) do seu especialista técnico da Épico e especifica o ambiente. Configure o máximo de URLs base FHIR conforme necessário, dependendo das necessidades da sua organização e dos ambientes que você deseja testar.

    - A URL base FHIR é um endereço estático que corresponde ao ponto de extremidade da API FHIR do servidor. Um exemplo de URL é `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.

    - Você pode configurar a integração para ambientes de teste e produção. Para a instalação inicial, recomendamos que você configure o conector de um ambiente de teste antes de ir para a produção.

1. Adiciona o nome de usuário do analista de clientes épico que aprovará a configuração em uma etapa posterior.

    :::image type="content" source="media/ehr-connector-epic-configure.png" alt-text="Captura de tela da página Configuração, mostrando o aprovador sendo adicionado." lightbox="media/ehr-connector-epic-configure.png":::

### <a name="enable-sms-notifications-optional"></a>Habilitar notificações SMS (opcional)

> [!NOTE]
> No momento, as notificações por SMS só estão disponíveis nos Estados Unidos. Estamos trabalhando para disponibilizar esse recurso em outras regiões em versões futuras do Teams e atualizará este artigo quando disponível.

Conclua esta etapa se sua organização quiser que a Microsoft gerencie notificações SMS para seus pacientes. Quando você habilita as notificações de SMS, seus pacientes receberão mensagens de confirmação e lembrete para visitas agendadas.

Para habilitar notificações sms, o administrador Microsoft 365 faz o seguinte:

1. Na página Notificações por SMS, selecione as duas caixas de seleção de consentimento para:

    - Permita que a Microsoft envie notificações SMS para os pacientes em nome da sua organização.
    - Confirme se você garantirá que os participantes consentiram em enviar e receber mensagens SMS.
    
    :::image type="content" source="media/ehr-connector-epic-sms-notifications.png" alt-text="Captura de tela da página notificações sms, mostrando caixas de seleção de consentimento e a opção de gerar um número de telefone." lightbox="media/ehr-connector-epic-sms-notifications.png":::

1. Em **Seus números de telefone**, selecione **Gerar um novo número de telefone** para gerar um número de telefone para sua organização. Isso inicia o processo para solicitar e gerar um novo número de telefone. Esse processo pode levar até 2 minutos para ser concluído.

    Depois que o número de telefone é gerado, ele é exibido na tela. Esse número será usado para enviar confirmações de SMS e lembretes para seus pacientes. O número foi provisionado, mas ainda não está vinculado à URL base FHIR. Faça isso na próxima etapa.

    :::image type="content" source="media/ehr-connector-epic-phone-number.png" alt-text="Captura de tela mostrando um exemplo do número de telefone gerado." lightbox="media/ehr-connector-epic-phone-number.png":::

    Escolha **Feito** e selecione **Próximo**.

1. Para vincular o número de telefone a uma URL base FHIR, **em Telefone na** seção **configuração SMS**, selecione o número. Faça isso para cada URL base FHIR para a qual você deseja habilitar notificações SMS.

    :::image type="content" source="media/ehr-connector-epic-link-phone-number.png" alt-text="Captura de tela mostrando como vincular um número de telefone a uma URL base FHIR." lightbox="media/ehr-connector-epic-link-phone-number.png":::

    Se essa for a primeira vez que você estiver configurando o conector, você verá a URL base FHIR inserida na etapa anterior. O mesmo número de telefone pode ser vinculado a várias URLs base FHIR, o que significa que os pacientes receberão notificações SMS do mesmo número de telefone para organizações e/ou departamentos diferentes.

1. Selecione **a configuração de SMS** ao lado de cada URL base FHIR para configurar os tipos de notificações SMS para enviar aos seus pacientes.

    :::image type="content" source="media/ehr-connector-epic-sms-setup.png" alt-text="Captura de tela mostrando configurações de configuração de SMS." lightbox="media/ehr-connector-epic-sms-setup.png":::

    - **SMS de confirmação**: As notificações são enviadas aos pacientes quando uma visita é agendada, atualizada ou cancelada no sistema EHR.
    - **Lembrete SMS**: As notificações são enviadas aos pacientes de acordo com o intervalo de tempo especificado e a hora agendada da visita.

    Escolha **Salvar**.

1. Selecione **Upload certificado para** carregar um certificado de chave pública. Você deve carregar um certificado .cer codificado em Base64 (somente chave pública) para cada ambiente.

    Um certificado de chave pública é necessário para receber informações de compromisso para o envio de notificações SMS. O certificado é necessário para verificar se as informações de entrada são de uma fonte válida.

    Quando o conector é usado para enviar lembretes de SMS, o número de telefone do paciente é enviado pela Epic em uma carga HL7v2 quando os compromissos são criados na Épico. Esses números são armazenados para cada compromisso na geografia da sua organização e são mantidos até que o compromisso seja realizado. Para saber mais sobre como configurar mensagens HL7v2, consulte o Guia de Integração [Microsoft Teams Telehealth.](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357)

    Escolha **Próximo**.

> [!NOTE]
> A qualquer momento, o administrador Microsoft 365 pode atualizar qualquer uma das configurações de SMS. Lembre-se de que a alteração das configurações pode resultar em uma parada do serviço SMS. Para obter mais informações sobre como exibir relatórios SMS, [consulte Teams de administrador do conector EHR](ehr-admin-reports.md).

### <a name="approve-or-view-the-configuration"></a>Aprovar ou exibir a configuração

O analista de clientes épico em sua organização que foi adicionado como aprovador inicia o portal de configuração do conector [EHR](https://ehrconnector.teams.microsoft.com) e faz logor usando suas credenciais Microsoft 365 de segurança. Após a validação bem-sucedida, o aprovador é solicitado a entrar usando suas credenciais épicas para validar a organização Dalope.

> [!Note]
> Se o Microsoft 365 administrador e o analista de clientes épicos são a mesma pessoa, você ainda precisará entrar na Epic para validar seu acesso. A login é usada apenas para validar sua URL base FHIR. A Microsoft não armazenará credenciais ou acessará dados do EHR com essa entrada.

:::image type="content" source="media/ehr-connector-epic-login-approve.png" alt-text="Captura de tela da página Aprovar ou Exibir Configuração, mostrando a opção Logon e aprovar." lightbox="media/ehr-connector-epic-login-approve.png":::

Depois de entrar com êxito na Epic, o analista de clientes épico **deve** aprovar a configuração. Se a configuração não estiver correta, o administrador Microsoft 365 pode entrar no portal de configuração e alterar as configurações.

:::image type="content" source="media/ehr-connector-epic-approve.png" alt-text="Captura de tela da página Aprovar ou Exibir Configuração, mostrando a opção Aprovar." lightbox="media/ehr-connector-epic-approve.png":::

### <a name="review-and-finish-the-configuration"></a>Análise e conclua a configuração

Quando as informações de configuração forem aprovadas pelo administrador da Epic, você verá os registros de integração para o paciente e o provedor iniciarem. Os registros de integração incluem:

- Registros de pacientes e provedores
- Registro SMS direto
- Registro de configuração sms
- Registro de configuração de teste de dispositivo

O analista de clientes épico deve fornecer esses registros à Epic para concluir a configuração de Visitas Virtuais na Épico. Para obter mais informações, consulte o Guia de Integração [Microsoft Teams Telehealth.](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357)

> [!Note]  
> A qualquer momento, o Microsoft 365 ou o analista de cliente épico podem entrar no portal de configuração para exibir os registros de integração e alterar a configuração da organização, conforme necessário.

:::image type="content" source="media/ehr-connector-epic-finish.png" alt-text="Captura de tela da página Revisão e Concluir, mostrando informações de integração." lightbox="media/ehr-connector-epic-finish.png":::

> [!Note]
> O analista de clientes épico deve concluir o processo de aprovação para cada URL base FHIR configurada pelo administrador Microsoft 365 FHIR.

## <a name="launch-teams-virtual-visits"></a>Iniciar Teams virtuais

Depois de concluir as etapas do conector EHR e a configuração épica, sua organização está pronta para dar suporte a visitas de vídeo com Teams.

### <a name="virtual-visits-prerequisites"></a>Pré-requisitos de Visitas Virtuais

- Seus sistemas devem atender a todos os [requisitos de software e navegador](../../hardware-requirements-for-the-teams-app.md) para Teams.

- Você concluiu a configuração de integração entre a organização Dalope e sua Microsoft 365 organização.

### <a name="provider-experience"></a>Experiência do provedor

Os provedores de saúde de sua organização podem participar de visitas usando Teams aplicativos de provedor épicos (Hyperspace, Haiku, Canto). O botão **Iniciar visita virtual** está incorporado no fluxo do provedor.

Principais recursos da experiência do provedor:

- Os provedores podem participar de visitas usando navegadores com suporte ou o Teams aplicativo.

- Os provedores devem fazer uma login única com sua conta Microsoft 365 ao ingressar em uma visita pela primeira vez.

- Após a logon única, o provedor é levado diretamente para o compromisso virtual no Teams. (O provedor deve estar Teams).

- Os provedores podem ver atualizações em tempo real de participantes se conectando e desconectando para um determinado compromisso. Os provedores podem ver quando o paciente está conectado a uma visita.

  ![Experiência de provedor de uma visita com um paciente.](media/ehc-provider-experience-6.png)

> [!NOTE]
> Todas as informações inseridas no chat de reunião necessárias para fins de continuidade ou retenção de registros médicos devem ser baixadas, copiadas e notadas pelo provedor de saúde. O chat não constitui um registro médico legal ou um conjunto de registros designado. As mensagens do chat são armazenadas com base nas configurações criadas pelo Microsoft Teams administrador.

### <a name="patient-experience"></a>Experiência do paciente

O conector dá suporte a pacientes que ingressarem em visitas por meio do MyChart Web e mobile. No momento do compromisso, os pacientes podem iniciar uma visita do MyChart usando o **botão Iniciar visita virtual** .

Características principais da experiência do paciente:

- Os pacientes podem participar de visitas de navegadores da Web modernos na área de trabalho e em dispositivos móveis sem precisar instalar [o Teams app](../mobile-browser-join.md).

- Os pacientes podem participar de visitas com um único clique e nenhuma outra conta ou login é necessária.

- Os pacientes não são obrigados a criar uma conta da Microsoft ou entrar para iniciar uma visita.

- Os pacientes são colocados em um lobby até que o provedor insusse e os admita.

- Os pacientes podem testar seu vídeo e microfone no lobby antes de ingressar na visita.

  ![Experiência do paciente da visita.](media/ehc-virtual-visit-5.png)

> [!Note]
> Epic, MyChart, Haiku e Canto são marcas comerciais da Epic Systems Corporation.

### <a name="privacy-and-location-of-data"></a>Privacidade e localização de dados

Teams integração com sistemas EHR otimiza a quantidade de dados usados e armazenados durante a integração e fluxos de Visitas Virtuais. A solução segue os princípios e diretrizes gerais de privacidade e gerenciamento de dados do Teams, descritos em Privacidade do Teams.

O Teams EHR não armazena ou transfere dados pessoais identificáveis ou quaisquer registros de saúde de pacientes ou provedores de saúde do sistema EHR. Os únicos dados armazenados pelo conector EHR são a ID exclusiva do usuário EHR, que é usada durante a configuração da reunião do Teams.

A ID exclusiva do usuário EHR é armazenada em uma das três regiões geográficas descritas em [Onde seus dados de cliente Microsoft 365 são armazenados](/microsoft-365/enterprise/o365-data-locations). Todos os chats, gravações e outros dados compartilhados no Teams por participantes da reunião são armazenados de acordo com as políticas de armazenamento existentes. Para saber mais sobre a localização dos dados Teams, consulte [Local dos dados Teams](../../location-of-data-in-teams.md).

## <a name="related-articles"></a>Artigos relacionados

- [Teams de administrador do conector EHR](ehr-admin-reports.md)
- [Começar a Teams para organizações de saúde](teams-in-hc.md)
