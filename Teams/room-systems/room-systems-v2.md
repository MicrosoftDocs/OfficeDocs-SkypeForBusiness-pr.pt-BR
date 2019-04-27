---
title: Implantar salas de equipes da Microsoft
ms.author: Turgayo
author: Turgayo
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Leia este artigo para saber mais sobre como implantar o Microsoft equipes salas.
ms.openlocfilehash: e17d607a18729cef23d98fbe9e9baf0144c50b3e
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362568"
---
# <a name="deployment-overview"></a>Visão geral de implantação

Implantação do Microsoft equipes salas essencialmente é dividido em fases:

- Confirmando que seus locais de implantação (salas) atendam as dependências de implantação
- Criando Teams da Microsoft ou Skype para contas de negócios e do Exchange e atribuindo a elas nos dispositivos de console (consulte [Configurar contas para salas de equipes da Microsoft](room-systems-v2-configure-accounts.md))
- Fazer uma nova imagem Microsoft Surface tablets para funcionar como consoles de salas de equipes da Microsoft (consulte [Configure um console de salas de equipes da Microsoft](console.md) ou o [guia de implantação em massa de implantar o Microsoft equipes salas](room-systems-scale.md))
- (Opcional) Configurando o pacote de gerenciamento do Microsoft Operations para seus sistemas (consulte [gerenciamento de implantar o Microsoft equipes salas com Monitor do Azure](azure-monitor-deploy.md)
- Configurando consoles em salas de reunião e conectando-se a dispositivos periféricos você precisa (consulte a documentação de OEM para seu conjunto de dispositivos)

Os técnicos de AV podem ser usados para a última tarefa, mas sua organização departamento de TI será necessário fazer as outras partes do processo. 


## <a name="site-readiness"></a>Preparação de site 

Enquanto os dispositivos ordenados estão sendo entregues para sua organização, trabalhe com a sua rede e instalações e equipes de AV para certificar-se de que as dependências de implantação são atendidas e cada site e a sala está pronto em termos de energia, rede e exibir. Além disso, certifique-se dos que requisitos de instalação física foram atendidos. Para considerações sobre a instalação física, visite o site do fornecedor e aproveite a experiência da sua equipe de AV durante a instalação e montando telas e executando o cabeamento.

Você pode encontrar mais informações sobre essas dependências nos links de orientação planejamento abaixo:

-   [Verificar a disponibilidade da rede](srs-v2-prep.md#check-network-availability) 
-   [Certificados](srs-v2-prep.md#certificates)
-   [Proxy](srs-v2-prep.md#proxy)

**Dica pro** - se você pretende usar servidores proxy para fornecer acesso ao Microsoft Teams ou Skype para negócios Online, primeiro [Examine neste artigo](https://docs.microsoft.com/skypeforbusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online). Observe que, quando se trata de Skype para tráfego de negócios sobre servidores proxy, é recomendável ignorando servidores proxy todo. Skype para tráfego de negócios já é criptografado para que servidores proxy não tornam mais seguro. Como parte da sua implantação mais larga, recomendamos que você siga as orientações em [avaliar o meu ambiente](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#network-readiness) de largura de banda planejamento e avaliar a viabilidade da sua rede para tráfego em tempo real. Para o planejamento de largura de banda todos, use o [MyAdvisor Planejador de rede](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner). (É recomendável que você crie uma pessoa de salas de equipes da Microsoft para refletir o uso pretendido do Microsoft equipes salas [vídeo, compartilhamento de tela, áudio] e atribuir um número de usuários que corresponde ao número de unidades de salas de equipes da Microsoft a ser implantado para cada site.) 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Confirme que os sites atendem aos requisitos de chave de salas de equipes da Microsoft.</li><li>Confirme que você forneceu largura de banda suficiente para cada site.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Começa a planejar sua implantação de dispositivo e a configuração.</li></ul>| 

**Dica Pro-** Da perspectiva de planejamento de site por site, você pode achar ativos a seguir úteis. Eles abrangem mais do que apenas o Microsoft equipes salas e podem ser usados em uma distribuição completa do Skype para Business Online:

-   [Migração/distribuição de site entrega guia de planejamento](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_24)

-   [Site de distribuição e planejamento de migração - Playbook](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_16)

    > [!NOTE]
    > Conclua as tarefas na seção "4.3 – gt _ salas de conferência" playbook, sob a planilha de "4-pontos de extremidade" para cada site onde você estiver planejando implantar dispositivos de salas de equipes da Microsoft. Isso permitirá que você use a script posteriormente no processo de provisionamento de conta de em massa. 

## <a name="service-readiness"></a>Prontidão de serviço

Para preparar sua implantação de salas de equipes da Microsoft, faça o seguinte chave, tarefas central:

-   Defina os recursos de conta de serviço de salas de equipes da Microsoft.
-   Preparar uma unidade organizacional e o grupo do Active Directory para contas de serviço e mantenha sua máquina de salas de equipes da Microsoft e — opcionalmente — preparar os objetos de diretiva de grupo (GPOs) para habilitar a comunicação remota do PowerShell.

### <a name="define-microsoft-teams-rooms-service-account-features"></a>Definir os recursos de conta de serviço de salas de equipes da Microsoft 

Dependendo os cenários de colaboração que você decidiu habilitar com sua implantação de salas de equipes da Microsoft, você precisará determinar os recursos e capacidades que você atribuir a cada conta de serviço de salas de equipes da Microsoft que permitem que você.

| **Cenário** | **Descrição** | **Recurso de conta de serviço de salas de equipes da Microsoft** |
|---------- |------------- | --- |
| Reuniões interativas            | Usando a voz, vídeo e compartilhamento de tela; como um recurso bookable fazer as salas de equipes da Microsoft                     | Habilitado para Skype para os negócios, habilitados para o Exchange (caixa de correio de recursos) |
| Conferência discada            | Habilitar reuniões *diretamente* iniciado a partir do console de salas de equipes da Microsoft com as coordenadas de conferência discada | Habilitado para serviços de audioconferência                                          |
| Chamada de PSTN de saída/entrada | Habilitar o console de salas de equipes da Microsoft para fazer e receber chamadas PSTN                                         | Habilitado para o sistema telefônico                                                |

Para obter mais informações sobre contas de salas de equipes da Microsoft, consulte [Configurar contas para salas de equipes da Microsoft](room-systems-v2-configure-accounts.md).


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida quais cenários você suporte e identificar requisitos de licenciamento para suas contas de serviço de salas de equipes da Microsoft.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Prepare para hospedar máquina e contas de serviço.</li></ul>| 


_Conta de serviço do Microsoft equipes salas amostra tabela de planejamento_

| **Site**  | **Nome da sala** | **Tipo de sala** | **Recursos de sala futuras**                                                 | **Recursos de conta da Microsoft equipes salas**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| Matriz de Londres | Curie         | Média        | 1 tela, áudio e vídeo plus apresentação <br>Acesso de conferência discada<br> Acesso ao PSTN  | Habilitado para Skype para os negócios, habilitados para o Exchange (caixa de correio de recursos) <br>Habilitado para serviços de audioconferência <br>Habilitado para o sistema telefônico |
| Matriz de Sidnei | Hill          | Grande         | 2 telas, áudio e vídeos plus apresentação<br>Acesso de conferência discada<br> Acesso ao PSTN  | Habilitado para Skype para os negócios, habilitados para o Exchange (caixa de correio de recursos)<br> Habilitado para serviços de audioconferência <br>Habilitado para o sistema telefônico |


### <a name="prepare-to-host-microsoft-teams-rooms-machine-and-service-accounts-optional"></a>Preparar para hospedar máquina de salas de equipes da Microsoft e (opcionais) de contas de serviço

Para permitir que você gerencie e reportar sobre suas salas de equipes da Microsoft máquina e contas de serviço, prepare seu local do Active Directory ou o Azure Active Directory (AD Azure). 

Definir um grupo de Active Directory ou o Azure AD local para adicionar todas as contas de serviço (usuário) de salas de equipes da Microsoft para e criar relatórios de uso usando o cmdlet Get-CSUserSession PowerShell em sua implantação de salas de equipes da Microsoft. Por exemplo, crie um grupo chamado SkypeRoomSystemsv2 contas de serviço. 


Defina uma unidade organizacional na sua hierarquia de Active Directory ou o Azure AD local para armazenar todas as contas de máquina de salas de equipes da Microsoft (se ele estiver associados ao domínio) e uma unidade organizacional para armazenar todas as contas de usuário de salas de equipes da Microsoft. Se você criar uma unidade organizacional para as contas de máquina de salas de equipes da Microsoft, considere a desabilitação de herança para garantir que você aplique apenas as diretivas que você deve aplicar a salas de equipes da Microsoft de domínio. 

Crie um objeto de diretiva de grupo atribuído à unidade organizacional que contém suas contas de computador de salas de equipes da Microsoft. Use essa opção para: 

-   [Definir configurações de conta local e alimentação](room-systems-v2-operations.md#configuring-group-policy-for-microsoft-teams-rooms).
-   Habilite o Windows Update.
-   Habilite a comunicação remota do PowerShell. Você pode configurar um script de inicialização para executar um script simples: Enable-PSRemoting - Force

Você pode usar o PowerShell para realizar um número de atividades de gerenciamento remoto, incluindo Obtendo e configurando as informações de configuração. PowerShell remoto deve ser habilitado *antes de* qualquer PowerShell gerenciamento remoto pode demorar coloque e devem ser considerados como parte de seus processos de implantação ou configurados por meio da diretiva de grupo. Para obter mais informações sobre esses recursos e ativá-los, consulte [operações e manutenção](room-systems-v2-operations.md#remote-management-using-powershell). 


## <a name="configuration-and-deployment"></a>Configuração e implantação 

Planejamento para configuração e implantação aborda as seguintes áreas principais:

-   Provisionamento de contas
-   Instalação de software de dispositivo
-   Implantação de dispositivo
-   Aplicativo de salas de equipes da Microsoft e a configuração de dispositivos periféricos
-    Testes
-   Gerenciamento de ativos

### <a name="account-provisioning"></a>Provisionamento de contas 

Cada dispositivo Microsoft equipes salas requer uma conta de recurso dedicado e exclusivo que deve ser habilitada para o Microsoft Teams ou o Skype para Exchange e de negócios. Essa conta deve ter uma caixa de correio de sala hospedada no Exchange e ser habilitada como uma sala de reunião de equipes ou Skype para implantação de negócios. No lado do Exchange, o processamento de calendário deve ser configurado para que o dispositivo pode aceitar automaticamente solicitações de reunião recebidas. Para obter mais informações sobre como criar essas contas, consulte [Configurar contas para salas de equipes da Microsoft](room-systems-v2-configure-accounts.md). 

**Dica pro** – tornar a exibição nomes para essas contas descritivo e fácil de entender. Estes são os nomes que os usuários verão quando pesquisando e adicionando sistemas de salas de equipes da Microsoft para reuniões. Algumas organizações usam a convenção de *Site*-o*Nome da sala*(*Capacidade máxima de sala*)-RS, então, por exemplo, Curie — uma sala de conferência de 12-pessoa em Londres — podem ter o nome de exibição LON-CURIE (12)-RS. 

Se sua organização tiver várias salas de conferências que exigem vários, contas provisionadas, convém usar [Scripts de provisionamento de contas do Skype sala sistemas](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_2_0_4,5_2_0_5) para em massa-provisão várias contas de serviço de forma automática.


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida a convenção de nomenclatura para suas contas de salas de equipes da Microsoft.</li><li>Decida se você vai criar contas individuais ou use scripts de provisionamento em massa.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Começa a planejar sua implantação do dispositivo.</li></ul>| 


### <a name="device-software-installation"></a>Instalação de software de dispositivo 

Ao planejar implantar salas de equipes da Microsoft, você tem um número de opções a serem considerados para instalar o software necessário. Situações comuns e as abordagens são descritas na tabela a seguir. 

| **Cenário**            | **Abordagem**         |
|-------------------------|-----------------------|   
|Implantando um pequeno número de dispositivos de salas de equipes da Microsoft (<10). | Se usando Surface Pro – com base em salas de equipes da Microsoft, siga as [instruções de instalação para por dispositivo instalar](console.md). [Este vídeo à mão o orienta durante o processo.](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) Se estiver usando uma solução integrada, implantado por meio da imagem de fornecedor e definir configurações, conforme necessário. |
| Implantando entre 10 e 50 dispositivos de um fornecedor único.     | Criar uma imagem baseada em WIM, pausar após a [etapa 6 neste guia](console.md)e capturar uma imagem de distribuição a ser usado com a tecnologia de distribuição clonagem.    |
| Implementando mais de 50 dispositivos de salas de equipes da Microsoft, implantando dispositivos a partir de mais de um fornecedor ou a necessidade de agentes de específicas da organização como parte da implantação. | Use uma tarefa baseadas em sequencer construção e distribuição plataforma de software, como o [System Center Configuration Manager](room-systems-scale.md).  |

**Dica pro** - Each salas de equipes Microsoft deve ter um nome de máquina válido e exclusivo em sua rede. Muitos de monitoramento e alerta sistemas exibem o nome da máquina como um identificador de chave, portanto, é importante desenvolver uma convenção de nomenclatura para implantações de salas de equipes da Microsoft que permite que o pessoal de suporte localizarem facilmente as salas de equipes Microsoft que foi sinalizado como exigir uma ação. Um exemplo pode estar usando um padrão de*Site*MTR --o*Nome da sala* (MTR-LON-CURIE). 

Como parte da implantação, você também precisará considerar sua estratégia para gerenciar e configurar as [contas locais](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts) que são criados pelo instalador do aplicativo Microsoft equipes salas.

Podemos fornecer orientação sobre como usar o [Microsoft Azure Monitor](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) para monitorar a implantação de salas de equipes da Microsoft e reportar sobre disponibilidade, erros de hardware e software e versão do aplicativo Microsoft equipes salas. Se você decidir usar o pacote de gerenciamento de operações do Microsoft, você deve instalar o agente do pacote de gerenciamento de operações como parte do processo de instalação de software e configurar as informações de conexão do espaço de trabalho do seu espaço de trabalho. 

Uma consideração adicional é se as salas de equipes da Microsoft serão associados a um domínio. Informações sobre os benefícios da associação de domínio podem ser encontradas em [Considerações de ingresso de domínio do sistema de sala Skype](domain-joining-considerations.md). 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida a convenção de nomenclatura de dispositivo de salas de equipes da Microsoft a ser usado durante a implantação.</li><li>Decida se você vai ingressar dispositivos de salas de equipes da Microsoft para seu domínio e como gerenciar e configurar as contas locais. </li><li>Decida se irá usar o pacote de gerenciamento de operações para monitorar a implantação de salas de equipes da Microsoft.</li><li>Decida qual método você usará para implantar o software e os agentes para o sistema de salas de equipes da Microsoft em preparação para a implantação de dispositivo. </li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Começa a planejar sua abordagem de implantação de dispositivo.</li></ul>| 


### <a name="device-deployment"></a>Implantação de dispositivo

Depois que você implantou o software para as unidades de salas de equipes da Microsoft, crie seu plano de enviar os dispositivos e seus dispositivos periféricos atribuídos para suas salas e prossiga para a instalação e configuração. 


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida quem irá gerenciar a implantação de site por site.</li><li> Identifique os recursos que instalará os dispositivos de salas de equipes da Microsoft no site e realizar a configuração e testes.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Inicie o dispositivo de teste.</li></ul>| 

_Tabela de implantação de exemplo_

| **Site**  | **Nome da sala** | **Tipo de sala** | **Sistema de salas de equipes da Microsoft**  | **Dispositivos periféricos**  | **Nome do computador de salas de equipes da Microsoft**  | **Conta do recurso de salas de equipes da Microsoft**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| Matriz de Londres | Curie         | Média        |                                   |                  |                                          |                                             |
| Matriz de Sidnei | Hill          | Grande         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Aplicativo de salas de equipes da Microsoft e a configuração de dispositivos periféricos 

Após cada salas de equipes da Microsoft sistema tenha sido implantado fisicamente e os dispositivos periféricos compatíveis conectados, você precisará configurar o aplicativo Microsoft equipes salas para atribuir a conta do recurso de salas de equipes da Microsoft e a senha criada anteriormente , para permitir que o sistema de salas de equipes da Microsoft para entrar no Microsoft Teams ou Skype para Exchange e de negócios. Dele chave aproveitar periféricos certificados para o áudio e vídeos do USB vinculados a outro lugar no documento. Se não fizer isso pode resultar em comportamento imprevisível. 

Você pode configurar manualmente cada sistema salas de equipes da Microsoft. Como alternativa, você pode usar um armazenada centralmente, salas de equipes – Microsoft arquivo de configuração XML para gerenciar as configurações do aplicativo e aproveitar um script de inicialização do GPO para reaplicar a configuração desejada, cada vez que o sistema de salas de equipes da Microsoft é inicializado. 

Para obter mais informações sobre como usar o arquivo de configuração XML, consulte [Gerenciar configurações de console um Microsoft equipes salas remotamente com um arquivo de configuração XML](xml-config-file.md). 

Você pode usar o [PowerShell remoto](room-systems-v2-operations.md#remote-management-using-powershell) para receber a configuração de salas de equipes da Microsoft para fins de relatório. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida se você vai configurar cada sistema Microsoft equipes salas manualmente ou usar um arquivo XML de central (um por dispositivo de salas de equipes da Microsoft).</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Defina sua abordagem de gerenciamento remoto.</li></ul>| 

### <a name="testing"></a> Testes

Após ter sido implantado o sistema de salas de equipes da Microsoft, você deve testá-lo. Verifique se os recursos listados na [Ajuda do Microsoft equipes salas](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) está funcionando no dispositivo implantado. É altamente recomendável que a equipe de implantação Verifique que as salas de equipes da Microsoft está fazendo logon em um pacote de gerenciamento do Microsoft Operations (se usado). Também é importante que você faça um número de reuniões e chamadas de teste para verificar a qualidade. Para obter mais informações, consulte essa [lista de verificação de implantação útil](console.md#microsoft-teams-rooms-deployment-checklist).

É recomendável que como parte do Skype ou equipes gerais para distribuição de negócios, você configurar os arquivos de construção para painel de controle de qualidade de chamada (CQD), monitorar as tendências de qualidade e participar do processo de revisão de qualidade da experiência. Para obter mais informações, consulte o [Guia de revisão do Quality of Experience](https://aka.ms/qerguide). 

**Dica pro** – a [Matriz de teste](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) disponíveis a partir de [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) contém uma guia com um número de testes de salas de equipes da Microsoft que você deve examinar usando como parte do seu teste. 

### <a name="asset-management"></a>Gerenciamento de ativos 

Como parte da implantação, você vai querer atualizar seu registro ativo com o nome da sala, o nome do dispositivo de salas de equipes da Microsoft, conta do recurso entrou no Microsoft equipes salas e atribuído dispositivos periféricos (e quais portas USB usarem). 

_Tabela de ativos de exemplo_

| **Site**  | **Nome da sala** | **Tipo de sala** | **Salas de equipes da Microsoft não serial.**  | **Dispositivos periféricos / Serial n º portas /**  | **Nome do computador de salas de equipes da Microsoft**  | **Conta de serviço de salas de equipes da Microsoft**  | **Data implantada** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| Matriz de Londres | Curie         | Média        |                                          |                                          |                                          |                                            |                   |
| Matriz de Sidnei | Hill          | Grande         |                                          |                                          |                                          |                                            |                   |


