---
title: Verifique sua conexão com a Internet Teams Telefone com o Plano de Chamada
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f28350c2ae0487ed62d55bbd99d6a731a7bfac0
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2022
ms.locfileid: "61766914"
---
# <a name="check-your-internet-connection-for-teams-phone"></a>Verifique sua conexão com a Internet Teams Telefone

Teams Telefone é a tecnologia da Microsoft para habilenciar recursos de telefone em Microsoft Teams usando a Microsoft 365 nuvem. Cada dispositivo que usa Microsoft Teams e Teams Telefone precisa de uma conexão com a Internet.

Para obter a melhor Teams Telefone, você precisa de uma conexão de internet de banda larga que possa suportar o número máximo de chamadas telefônicas que sua organização pode fazer a qualquer momento. Você também precisa garantir que os computadores em sua rede possam alcançar Microsoft 365 serviços.

Você não precisa de uma Teams Telefone para seguir estas etapas.

## <a name="check-your-internet-connection-speed"></a>Verificar a velocidade da conexão com a Internet

Este artigo ajuda a determinar se sua conexão com a Internet é rápida o suficiente para o número de pessoas que precisam fazer chamadas telefônicas. Você fornecerá informações sobre sua organização e obterá de volta um relatório que mostra quanto da sua conexão com a Internet será usada por Teams e Teams Telefone.

### <a name="gather-information-about-your-internet-connection-and-users"></a>Coletar informações sobre sua conexão com a Internet e usuários

Antes de começar, você precisa das seguintes informações:

* A velocidade da conexão com a Internet
* Quantas pessoas usarão Teams Telefone principalmente do seu escritório
* Quantas pessoas usarão Teams Telefone de um local remoto, como um home office

### <a name="enter-your-information-into-the-network-planner"></a>Inserir suas informações no planejador de rede

Siga estas etapas:

1. Em um navegador, vá até [https://admin.teams.microsoft.com](https://admin.teams.microsoft.com). Entre usando uma conta que tenha permissões de Administrador Global. A conta que você usou para se inscrever no Microsoft 365 ou Office 365 tem essas permissões.
2. Abra **Planejamento** e selecione **Planejador de rede**.
3. Em **Planos de rede**, selecione **Adicionar**. Digite um nome ao seu plano e selecione **Aplicar**.
4. Selecione o nome do seu plano de rede.
5. Na próxima página, selecione **Adicionar um site de rede** na guia **Sites de rede**.
6. Preencha os campos **Nome do site de rede,** **Usuários** de Rede e Capacidade do link da **Internet** e selecione **Salvar**. Deixe os outros campos na tela em branco e não selecione as opções **ExpressRoute** ou **Conectado à WAN**.
7. Na guia **Relatório**, selecione **Iniciar um relatório**.
8. Insira um **nome de** relatório e o número de usuários de  rede **(** **Office** **e Remoto**) e selecione Gerar relatório para criar um relatório que mostra os requisitos de largura de banda para Teams. Informaremos como ler o relatório na próxima seção.

### <a name="find-your-minimum-internet-connection-speed"></a>Encontre a velocidade mínima de conexão com a Internet

Quando você seleciona **Gerar relatório,** Microsoft 365 ou Office 365 cria um relatório.

Na coluna **Impacto** e na **linha** Office 365, esse número mostra quanto da sua conexão Teams e Teams Telefone usar. Recomendamos que esse número não seja superior a 30% da velocidade total de conexão com a Internet. Por exemplo, se sua conexão com a Internet for *de 60 Mbps,* Teams e Teams Telefone deve usar no máximo *18 Mbps*.

Use esta equação para determinar sua velocidade mínima de conexão com a Internet: <Número de *impacto> / 0,3*.  

Digamos que o número de impacto seja *4,6875 Mbps*. O cálculo para encontrar sua velocidade mínima de conexão com a Internet seria *4,6875 / 0,3 = 15,6*. Nesse caso, a velocidade de conexão com a Internet deve ser de pelo menos *15,6 Mbps*.

Se Teams e Teams Telefone usar mais de 30% da velocidade total da conexão com a Internet, o número **de** impacto aparecerá vermelho. Nesse caso, talvez seja necessário atualizar sua conexão com a Internet.

![Aviso de velocidade de conexão.](../media/network-planner-report-speed-warning.png)

>[!NOTE]
> O impacto de largura de banda fornecido pelo Planejador de Rede é apenas uma estimativa. É recomendável usar o Painel de Qualidade de [Chamada](../cqd-what-is-call-quality-dashboard.md) para monitorar proativamente a experiência do usuário para chamadas de áudio e vídeo com Microsoft Teams dentro da sua organização.

## <a name="make-sure-the-computers-and-devices-on-your-network-can-reach-microsoft-365"></a>Verifique se os computadores e dispositivos da rede podem acessar o Microsoft 365

Computadores e dispositivos que usam Teams Telefone devem usar portas de rede específicas para se comunicar com Microsoft 365 serviços. Essas portas são essencialmente portas pelas quais os dispositivos conversam uns com os outros por meio de uma rede ou da Internet. O firewall deve permitir que os dispositivos em sua rede cheguem ao Microsoft 365 através das seguintes portas de rede de *saída*:

* **Portas TCP** 80 e 443
* **Portas UDP** 3478, 3479, 3480 e 3481

A maneira mais fácil de verificar se o firewall permite a comunicação nessas portas de rede é executar um teste de conectividade usando [a](/microsoft-365/enterprise/office-365-network-mac-perf-onboarding-tool) ferramenta de conectividade de rede Microsoft 365 do local do office que você deseja testar. Após concluir o teste, verifique os resultados e recomendações.
