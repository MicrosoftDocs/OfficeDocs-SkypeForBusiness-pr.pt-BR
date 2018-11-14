---
title: Implantar o Skype Room Systems versão 2
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
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Leia este artigo para saber mais sobre como implantar sistemas de sala Skype v2.
ms.openlocfilehash: 39704e044d5a5210d47a0347790f5602a3086270
ms.sourcegitcommit: 5d8b5dee1dea84494aea92bbce568dea10752af9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2018
ms.locfileid: "26510642"
---
# <a name="deployment-overview"></a>Visão geral de implantação

Implantação de sistemas de sala Skype v2 essencialmente é dividido em fases:

- Confirmando que seus locais de implantação (salas) atendam as dependências de implantação
- Criando Skype para contas de negócios e do Exchange e atribuindo a elas nos dispositivos de console (consulte [Configurar contas para sistemas de sala Skype v2](room-systems-v2-configure-accounts.md))
- Fazer uma nova imagem Microsoft Surface tablets para funcionar como consoles de v2 de sistemas de sala Skype (consulte [Configure um console do Skype sala sistemas v2](console.md) ou o [guia de implantação em massa implantar sistemas de sala Skype v2](room-systems-scale.md))
- (Opcional) Configurando o pacote de gerenciamento do Microsoft Operations para seus sistemas (consulte [gerenciamento de v2 implantar sistemas do Skype sala com OMS](with-oms.md))
- Configurando consoles em salas de reunião e conectando-se a dispositivos periféricos você precisa (consulte a documentação de OEM para seu conjunto de dispositivos)

Os técnicos de AV podem ser usados para a última tarefa, mas sua organização departamento de TI será necessário fazer as outras partes do processo. 


## <a name="site-readiness"></a>Preparação de site 

Enquanto os dispositivos ordenados estão sendo entregues para sua organização, trabalhe com a sua rede e instalações e equipes de AV para certificar-se de que as dependências de implantação são atendidas e cada site e a sala está pronto em termos de energia, rede e exibir. Além disso, certifique-se dos que requisitos de instalação física foram atendidos. Para considerações sobre a instalação física, visite o site do fornecedor e aproveite a experiência da sua equipe de AV durante a instalação e montando telas e executando o cabeamento.

Você pode encontrar mais informações sobre essas dependências nos links de orientação planejamento abaixo:

-   [Verificar a disponibilidade da rede](../../plan-your-deployment/clients-and-devices/srs-v2-prep.md#check-network-availability) 
-   [Certificados](../../plan-your-deployment/clients-and-devices/srs-v2-prep.md#certificates)
-   [Proxy](../../plan-your-deployment/clients-and-devices/srs-v2-prep.md#proxy)

**Dica pro** - se você pretende usar servidores proxy para fornecer acesso ao Skype para negócios Online, primeiro [Examine neste artigo](https://docs.microsoft.com/skypeforbusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online). Observe que, quando se trata de Skype para tráfego de negócios sobre servidores proxy, é recomendável ignorando servidores proxy todo. Skype para tráfego de negócios já é criptografado para que servidores proxy não tornam mais seguro. Como parte da sua mais larga Skype para implantação de negócios, recomendamos que você siga as orientações em [avaliar o meu ambiente](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#network-readiness) de largura de banda planejamento e avaliar a viabilidade da sua rede para tráfego em tempo real. Para o planejamento de largura de banda todos, use o [MyAdvisor Planejador de rede](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner). (É recomendável que você crie uma pessoa v2 de sistemas de sala Skype para refletir o uso pretendido do Skype sala sistemas v2 [vídeo, compartilhamento de tela, áudio] e atribuir um número de usuários que corresponde ao número de unidades de sistemas de sala Skype para ser implantada em cada site.) 

|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Confirme que os sites atendem aos requisitos de chave de sistemas de sala Skype v2.</li><li>Confirme que você forneceu largura de banda suficiente para cada site.</li></ul>| 
| ![](../../media/audio_conferencing_image9.png)<br/>Próximos passos|<ul><li>Começa a planejar sua implantação de dispositivo e a configuração.</li></ul>| 

**Dica Pro-** Da perspectiva de planejamento de site por site, você pode achar ativos a seguir úteis. Eles abrangem mais do que apenas de sistemas de sala Skype v2 e podem ser usados em uma distribuição completa do Skype para Business Online:

-   [Migração/distribuição de site entrega guia de planejamento](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_24)

-   [Site de distribuição e planejamento de migração - Playbook](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_16)

    > [!NOTE]
    > No playbook, preencha as tarefas na seção "4.3 – > salas de conferência" sob a planilha de "4-pontos de extremidade" para cada site onde você estiver planejando implantar sistemas de sala Skype v2 dispositivos. Isso permitirá que você use a script posteriormente no processo de provisionamento de conta de em massa. 

## <a name="service-readiness"></a>Prontidão de serviço

Para preparar sua implantação do Skype sistemas de sala, faça o seguinte chave, tarefas central:

-   Defina os recursos de sistemas de sala Skype de contas de serviço.
-   Preparar uma unidade organizacional e o grupo do Active Directory para manter sua máquina Skype sistemas de sala e contas de serviço e — opcionalmente — preparar os objetos de diretiva de grupo (GPOs) para habilitar a comunicação remota do PowerShell.

### <a name="define-skype-room-systems-service-account-features"></a>Definir os recursos de conta de serviço de sistemas de sala do Skype 

Dependendo os cenários de colaboração que você decidiu habilitar com sua implantação do Skype sala sistemas v2, você precisará determinar os recursos e capacidades que você atribuir a cada conta de serviço do Skype sala sistemas v2 que permitem que você.

| **Cenário** | **Descrição** | **Recurso de conta de serviço do Skype sala sistemas v2** |
|---------- |------------- | --- |
| Reuniões interativas            | Usando a voz, vídeo e compartilhamento de tela; tornando o v2 de sistemas de sala Skype um recurso bookable                     | Habilitado para Skype para os negócios, habilitados para o Exchange (caixa de correio de recursos) |
| Conferência discada            | Habilitar reuniões iniciado *diretamente* no console do v2 Skype sala sistemas com as coordenadas de conferência discada | Habilitado para serviços de audioconferência                                          |
| Chamada de PSTN de saída/entrada | Habilitar o console de v2 de sistemas de sala Skype façam e recebam chamadas PSTN                                         | Habilitado para o sistema telefônico                                                |

Para obter mais informações sobre contas de sistemas de sala Skype, consulte [Configurar contas para sistemas de sala Skype v2](room-systems-v2-configure-accounts.md).


|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida quais cenários você suporte e identificar requisitos de licenciamento para suas contas de serviço do Skype sala sistemas v2.</li></ul>| 
| ![](../../media/audio_conferencing_image9.png)<br/>Próximos passos|<ul><li>Prepare para hospedar máquina e contas de serviço.</li></ul>| 


_Conta de serviço do exemplo Skype sala sistemas v2 tabela de planejamento_

| **Site**  | **Nome da sala** | **Tipo de sala** | **Recursos de sala futuras**                                                 | **Recursos de conta v2 de sistemas de sala do Skype**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| Matriz de Londres | Curie         | Médio        | 1 tela, áudio e vídeo plus apresentação <br>Acesso de conferência discada<br> Acesso ao PSTN  | Habilitado para Skype para os negócios, habilitados para o Exchange (caixa de correio de recursos) <br>Habilitado para serviços de audioconferência <br>Habilitado para o sistema telefônico |
| Matriz de Sidnei | Hill          | Grande         | 2 telas, áudio e vídeos plus apresentação<br>Acesso de conferência discada<br> Acesso ao PSTN  | Habilitado para Skype para os negócios, habilitados para o Exchange (caixa de correio de recursos)<br> Habilitado para serviços de audioconferência <br>Habilitado para o sistema telefônico |


### <a name="prepare-to-host-skype-room-systems-v2-machine-and-service-accounts-optional"></a>Preparar-se para a máquina host v2 Skype sistemas de sala e (opcionais) de contas de serviço

Para permitir que você gerencie e relatar em sua máquina de v2 Skype sistemas de sala e contas de serviço, preparar seu local do Active Directory ou o Azure Active Directory (AD Azure). 

Definir um grupo de Active Directory ou o Azure AD local para adicionar todas as contas de serviço (usuário) de sistemas de sala do Skype v2 para e criar relatórios de uso usando o cmdlet Get-CSUserSession PowerShell em sua implantação do Skype sala sistemas v2. Por exemplo, crie um grupo chamado SkypeRoomSystemsv2 contas de serviço. 


Defina uma unidade organizacional na sua hierarquia de Active Directory ou o Azure AD local para armazenar todas as contas de máquina do Skype sala sistemas v2 (se ele estiver associados ao domínio) e uma unidade organizacional para armazenar todas as contas de usuário de v2 Skype sistemas de sala. Se você criar uma unidade organizacional para as contas de máquina do Skype sala sistemas v2, considere a desabilitação de herança para garantir que você aplique apenas as diretivas que você deve aplicar para o domínio Skype sala Systemsv2. 

Crie um objeto de diretiva de grupo atribuído à unidade organizacional que contém suas contas de computador do Skype sistemas de sala. Use essa opção para: 

-   [Definir configurações de conta local e alimentação](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#configuring-group-policy-for-skype-room-systems-v2).
-   Habilite o Windows Update.
-   Habilite a comunicação remota do PowerShell. Você pode configurar um script de inicialização para executar um script simples: Enable-PSRemoting - Force

Você pode usar o PowerShell para realizar um número de atividades de gerenciamento remoto, incluindo Obtendo e configurando as informações de configuração. PowerShell remoto deve ser habilitado *antes de* qualquer PowerShell gerenciamento remoto pode demorar coloque e devem ser considerados como parte de seus processos de implantação ou configurados por meio da diretiva de grupo. Para obter mais informações sobre esses recursos e ativá-los, consulte [operações e manutenção](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#remote-management-using-powershell). 


## <a name="configuration-and-deployment"></a>Configuração e implantação 

Planejamento para configuração e implantação aborda as seguintes áreas principais:

-   Provisionamento de contas
-   Instalação de software de dispositivo
-   Implantação de dispositivo
-   Aplicativo do Skype sala sistemas v2 e configuração de dispositivos periféricos
-    Testes
-   Gerenciamento de ativos

### <a name="account-provisioning"></a>Provisionamento de contas 

Cada dispositivo v2 de sistemas de sala Skype requer uma conta de recurso dedicado e exclusivo que deve ser habilitada para ambos os Skype para Exchange e de negócios. Essa conta deve ter uma caixa de correio de sala hospedada no Exchange e ser habilitada como uma sala de reunião no Skype para implantação de negócios. No lado do Exchange, o processamento de calendário deve ser configurado para que o dispositivo pode aceitar automaticamente solicitações de reunião recebidas. Para obter mais informações sobre como criar essas contas, consulte [Configurar contas para sistemas de sala Skype v2](room-systems-v2-configure-accounts.md). 

**Dica pro** – tornar a exibição nomes para essas contas descritivo e fácil de entender. Estes são os nomes que os usuários verão quando pesquisando e adicionando sistemas do Skype sala sistemas v2 para reuniões. Algumas organizações usam a convenção de *Site*-o*Nome da sala*(*Capacidade máxima de sala*)-RS, então, por exemplo, Curie — uma sala de conferência de 12-pessoa em Londres — podem ter o nome de exibição LON-CURIE (12)-RS. 

<!-- If your organization has many conference rooms that require multiple, provisioned accounts, you might want to use [Skype Room Systems Accounts Provisioning Scripts](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_2_0_4,5_2_0_5) to bulk-provision multiple service accounts in an automated fashion. -->


|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida a convenção de nomenclatura para suas contas de v2 Skype sistemas de sala.</li><li>Decida se você vai criar contas individuais ou use scripts de provisionamento em massa.</li></ul>| 
| ![](../../media/audio_conferencing_image9.png)<br/>Próximos passos|<ul><li>Começa a planejar sua implantação do dispositivo.</li></ul>| 


### <a name="device-software-installation"></a>Instalação de software de dispositivo 

Ao planejar implantar Skype sala Systemsv2, você tem um número de opções a serem considerados para instalar o software necessário. Situações comuns e as abordagens são descritas na tabela a seguir. 

| **Cenário**            | **Abordagem**         |
|-------------------------|-----------------------|   
|Implantando um pequeno número de dispositivos de sistemas de sala Skype (< 10). | Se usando Surface Pro – sistemas com base em Skype sala v2, siga as [instruções de instalação para por dispositivo instalar](console.md). [Este vídeo à mão o orienta durante o processo.](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) Se estiver usando uma solução integrada, implantado por meio da imagem de fornecedor e definir configurações, conforme necessário. |
| Implantando entre 10 e 50 dispositivos de um fornecedor único.     | Criar uma imagem baseada em WIM, pausar após a [etapa 6 neste guia](console.md)e capturar uma imagem de distribuição a ser usado com a tecnologia de distribuição clonagem.    |
| Implementando mais de 50 dispositivos de sistemas de sala Skype, Implementando dispositivos de mais de um fornecedor ou a necessidade de agentes de específicas da organização como parte da implantação. | Use uma tarefa baseadas em sequencer construção e distribuição plataforma de software, como o [System Center Configuration Manager](with-oms.md).  |

**Dica pro** - v2 de sistemas de sala Skype Each deve ter um nome de máquina válido e exclusivo em sua rede. Muitos de monitoramento e alerta sistemas exibem o nome da máquina como um identificador de chave, portanto, é importante desenvolver uma convenção de nomenclatura para implantações do Skype sala sistemas v2 que permite que o pessoal de suporte localizar facilmente os sistemas de sala Skype v2 que foi sinalizado como exigir uma ação. Um exemplo pode estar usando um padrão de SRS*Site*-o*Nome da sala* (SRS-LON-CURIE). 


Como parte da implantação, você também precisará considerar sua estratégia para gerenciar e configurar as [contas locais](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts) que são criados pelo instalador do aplicativo do Skype sistemas de sala.

Podemos fornecer orientação sobre como usar o [Pacote de gerenciamento do Microsoft Operations](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/oms-management) para monitorar a implantação do Skype sala sistemas v2 e reportar sobre disponibilidade, erros de hardware e software e versão do aplicativo do Skype sala sistemas v2. Se você decidir usar o pacote de gerenciamento de operações do Microsoft, você deve instalar o agente do pacote de gerenciamento de operações como parte do processo de instalação de software e configurar as informações de conexão do espaço de trabalho do seu espaço de trabalho. 

Uma consideração adicional é se o v2 Skype sala sistemas serão associados a um domínio. Informações sobre os benefícios da associação de domínio podem ser encontradas em [Considerações de ingresso de domínio do sistema de sala Skype](domain-joining-considerations.md). 

|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida a convenção de nomenclatura de dispositivo de sistemas de sala Skype a ser usado durante a implantação.</li><li>Decida se você vai ingressar dispositivos do Skype sala sistemas v2 para o seu domínio e como gerenciar e configurar as contas locais. </li><li>Decida se irá usar o pacote de gerenciamento de operações para monitorar a implantação de v2 Skype sistemas de sala.</li><li>Decida qual método você usará para implantar o software e os operadores ao sistema v2 Skype sala sistemas em preparação para a implantação de dispositivo. </li></ul>| 
| ![](../../media/audio_conferencing_image9.png)<br/>Próximos passos|<ul><li>Começa a planejar sua abordagem de implantação de dispositivo.</li></ul>| 


### <a name="device-deployment"></a>Implantação de dispositivo

Depois que você implantou o software para as unidades de v2 Skype sala sistemas, crie seu plano de enviar os dispositivos e seus dispositivos periféricos atribuídos para suas salas e prossiga para a instalação e configuração. 


|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida quem irá gerenciar a implantação de site por site.</li><li> Identifique os recursos que instalará os dispositivos de sistemas de sala Skype v2 no site e realizar a configuração e testes.</li></ul>| 
| ![](../../media/audio_conferencing_image9.png)<br/>Próximos passos|<ul><li>Inicie o dispositivo de teste.</li></ul>| 

_Tabela de implantação de exemplo_

| **Site**  | **Nome da sala** | **Tipo de sala** | **Sistema de v2 de sistemas de sala do Skype**  | **Dispositivos periféricos**  | **Nome do computador do Skype sala sistemas v2**  | **Conta do recurso de v2 de sistemas de sala do Skype**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| Matriz de Londres | Curie         | Médio        |                                   |                  |                                          |                                             |
| Matriz de Sidnei | Hill          | Grande         |                                   |                  |                                          |                                             |

### <a name="skype-room-systems-v2-application-and-peripheral-device-configuration"></a>Aplicativo do Skype sala sistemas v2 e configuração de dispositivos periféricos 

Depois que cada sistema v2 de sistemas de sala Skype tiver sido implantado fisicamente e os dispositivos periféricos compatíveis conectados, você precisará configurar o aplicativo de v2 de sistemas de sala Skype para atribuir a conta do recurso do Skype sala sistemas v2 e senha que criou anteriormente, para Habilite o sistema de v2 Skype sistemas de sala entrar no Skype para Exchange e de negócios. Chave aproveitar Skype para negócios certificada USB periféricos áudio e vídeos vinculados a outro lugar no documento-lo do. Se não fizer isso pode resultar em comportamento imprevisível. 

Você pode configurar manualmente cada sistema v2 de sistemas de sala Skype. Como alternativa, você pode usar um armazenada centralmente, sistemas de sala por Skype XML arquivo de configuração para gerenciar as configurações do aplicativo e aproveitar um script de GPO de inicialização para reaplicar a configuração desejada, cada vez que o sistema de v2 de sistemas de sala Skype é inicializado. 

Para obter mais informações sobre como usar o arquivo de configuração XML, consulte [as configurações do console de gerenciar um v2 Skype sala sistemas remotamente com um arquivo de configuração XML](../../manage/skype-room-systems-v2/xml-config-file.md). 

Você pode usar o [PowerShell remoto](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#remote-management-using-powershell) para receber a configuração do Skype sala sistemas v2 para fins de relatório. 

|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida se você vai configurar cada sistema v2 de sistemas de sala do Skype manualmente ou usar um arquivo XML de central (um por dispositivo do Skype sala sistemas v2).</li></ul>| 
| ![](../../media/audio_conferencing_image9.png)<br/>Próximos passos|<ul><li>Defina sua abordagem de gerenciamento remoto.</li></ul>| 

### <a name="testing"></a> Testes

Depois que o sistema de v2 de sistemas de sala Skype tiver sido implantado, você deve testá-lo. Verifique se os recursos listados na [Ajuda do Skype sala sistemas v2](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) estão funcionando no dispositivo implantado. É altamente recomendável que a equipe de implantação verificar que o v2 de sistemas de sala Skype está fazendo logon em um pacote de gerenciamento do Microsoft Operations (se usado). Também é importante que você faça um número de reuniões e chamadas de teste para verificar a qualidade. Para obter mais informações, consulte essa [lista de verificação de implantação útil](console.md#skype-room-systems-v2-deployment-checklist). 

É recomendável que como parte do Skype geral para distribuição de negócios, você configurar os arquivos de construção para painel de controle de qualidade de chamada (CQD), monitorar as tendências de qualidade e participar do processo de revisão de qualidade da experiência. Para obter mais informações, consulte o [Guia de revisão do Quality of Experience](https://aka.ms/qerguide). 

**Dica pro** – a [Matriz de teste](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) disponíveis a partir de [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) contém uma guia com um número de sistemas de sala Skype v2 testes que você deve examinar usando como parte do seu teste. 

### <a name="asset-management"></a>Gerenciamento de ativos 

Como parte da implantação, você vai querer atualizar seu registro ativo com o nome da sala, o nome do dispositivo do Skype sala sistemas v2, conta do recurso entrou no Skype sala sistemas v2 e atribuído dispositivos periféricos (e quais portas USB usarem). 

_Tabela de ativos de exemplo_

| **Site**  | **Nome da sala** | **Tipo de sala** | **Sistemas de sala Skype v2 não serial.**  | **Dispositivos periféricos / Serial n º portas /**  | **Nome do computador do Skype sala sistemas v2**  | **Conta de serviço do Skype sala sistemas v2**  | **Data implantada** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| Matriz de Londres | Curie         | Médio        |                                          |                                          |                                          |                                            |                   |
| Matriz de Sidnei | Hill          | Grande         |                                          |                                          |                                          |                                            |                   |


