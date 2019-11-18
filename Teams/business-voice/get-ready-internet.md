---
title: Verificar sua conexão com a Internet
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19f26c0bd7ab4fe89770909d81d60abc97aaa8b0
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2019
ms.locfileid: "38653547"
---
# <a name="check-your-internet-connection"></a>Verificar sua conexão com a Internet

O Business Voice está localizado na nuvem do Microsoft 365. Todo computador e dispositivo que usa o Microsoft Teams e o Business Voice precisa de uma conexão com a Internet. Para obter a melhor experiência com o Business Voice, é preciso uma conexão de Internet de banda larga que suporte o número esperado de chamadas telefônicas que serão feitas a qualquer momento. Também é preciso ter certeza de que os computadores da sua rede podem acessar os servidores do Microsoft 365.

Para seguir estas etapas, você precisa ter um locatário com uma das seguintes assinaturas:

* Office 365 Business Essentials
* Office 365 Business Premium
* Office 365 E1
* Office 365 E3
* Office 365 F1
* Microsoft 365 A1
* Microsoft 365 A3
* Microsoft 365 E3
* Microsoft 365 Business

Você não precisa de uma licença do Business Voice para seguir estas etapas.

## <a name="check-your-internet-connection-speed"></a>Verifique a velocidade da sua conexão com a Internet

Este artigo ajuda a determinar se a conexão com a Internet é rápida o suficiente para o número de pessoas que precisam fazer chamadas telefônicas, hospedar videoconferências e assim por diante. Você inserirá algumas informações sobre a organização e receberá um relatório com o quanto da sua conexão com a Internet será usada pelo Teams e Business Voice.

### <a name="get-information-about-your-internet-connection-and-users"></a>Obter informações sobre a conexão com a Internet e os usuários

Antes de começar, você precisa saber as seguintes informações:

* A velocidade da sua conexão com a Internet.
* Quantas pessoas usarão o Business Voice basicamente do seu escritório.
* Quantas pessoas usarão o Business Voice basicamente de um local remoto, como um escritório residencial.

### <a name="enter-your-information-into-the-network-planner"></a>Inserir suas informações no planejador de rede

Veja aqui o que você precisa fazer:

1. Abra um navegador e vá para https://admin.teams.microsoft.com, e entre com uma conta que tenha permissões de Administrador Global. A conta que você usou para se inscrever no Office 365 tem essas permissões.
1. Abra **Planejamento** e selecione **Planejador de rede**.
1. Em **Planos de rede**, selecione **Adicionar**. Dê um nome ao seu plano e selecione **Aplicar**. Seu plano de rede deve ter a seguinte aparência:

    ![Tela principal do Planejador de rede](../media/network-planner-main.png)
1. Clique no nome do seu plano de rede (**Escritório principal** na imagem acima).
1. Na próxima página, selecione **Adicionar um site de rede** na guia **Sites de rede**.
1. Preencha somente os campos indicados na captura de tela abaixo e, em seguida, selecione **Salvar**. Deixe os outros campos na tela em branco e não selecione as opções **ExpressRoute** ou **Conectado a WAN**.

    ![Informações do site do planejador de rede](../media/network-planner-site-info.png)
1. Na guia **Relatório**, selecione **Iniciar um relatório**.
1. Preencha as seguintes informações e, em seguida, selecione **Gerar relatório** para criar um relatório que mostre os requisitos de largura de banda para o Teams. Mostraremos como ler o relatório na próxima seção.

    ![Informações do relatório do planejador de rede](../media/network-planner-report-info.png)

### <a name="find-your-minimum-internet-connection-speed"></a>Encontre sua velocidade mínima de conexão com a Internet

Ao selecionar **Gerar relatório**, o Office 365 cria um relatório parecido com este:

![Detalhes do relatório do planejador de rede](../media/network-planner-report.png)

O número realçado mostra o quanto da sua conexão com a Internet será usada pelo Teams e Business Voice. Recomendamos que esse número não ultrapasse 30% da velocidade total da conexão com a Internet. Por exemplo, se a conexão com a Internet for 60 Mbps, O Teams e o Business Voice deverão ocupar no máximo 18 Mbps.

Você pode encontrar a sua velocidade mínima de conexão com a Internet fazendo este cálculo: `<highlighted number> / .3`. Usando o número realçado na figura acima, o cálculo seria `4.6875 / .3 = 15.6`. Isso significa que a velocidade mínima de conexão com a Internet precisa ser de pelo menos 15,6 Mbps.

Se o Teams e o Business Voice usarem mais de 30% da velocidade total da conexão com a Internet, o número realçado será mostrado em vermelho. Se isso acontecer, talvez seja necessário atualizar sua conexão com a Internet.

![Aviso de velocidade de conexão](../media/network-planner-report-speed-warning.png)

## <a name="make-sure-computers-and-devices-on-your-network-can-reach-microsoft-365"></a>Verifique se os computadores e dispositivos da rede podem acessar o Microsoft 365

Para funcionar corretamente, os computadores e dispositivos que você deseja usar com o Business Voice precisam se comunicar com os servidores Microsoft 365 usando portas de rede específicas. As portas de rede são essencialmente portas pelas quais computadores e dispositivos podem se comunicar por meio de uma rede ou da Internet. O firewall deve permitir que computadores e dispositivos na rede acessem o Microsoft 365 usando as seguintes portas de rede de saída:

* **Portas TCP** 80 e 443
* **Portas UDP** 3478, 3479, 3480 e 3481

A maneira mais fácil de verificar se o firewall permite a comunicação nas portas de rede é fazer uma chamada de teste usando o Teams. Para fazer uma chamada de teste, faça o seguinte:

1. Vá para https://aka.ms/getteams em um computador na rede para instalar o Teams. Verifique se os alto-falantes e um microfone estão conectados ao computador.
2. Abra o Teams e entre usando uma conta do Microsoft 365
3. No Teams, selecione sua foto do perfil e, em seguida, **Configurações** > **Dispositivos**
4. Escolha **Faça uma chamada de teste** em **Dispositivos de áudio**
5. Siga os avisos para deixar uma mensagem e reproduzi-la para você 

* Se a chamada for conectada e você conseguir ouvir a sua mensagem, seu firewall está configurado corretamente.
* Se a chamada for conectada, mas você não conseguir ouvir os avisos ou a sua mensagem, verifique se os alto-falantes e o microfone estão configurados corretamente e detectados pelo computador. Tente novamente.
* Se a chamada não se conectar ou se você não conseguir ouvir a sua mensagem, talvez seja necessário atualizar o firewall para permitir as portas de rede listadas acima. Verifique a documentação do firewall sobre como permitir que as portas de rede acessem a Internet ou entre em contato com um especialista de TI para ajudá-lo.

Se você é um profissional de TI e deseja obter mais informações sobre como preparar redes maiores ou mais complexas para dar suporte ao Business Voice, dê uma olhada em [Avaliar meu ambiente](../3-envision-evaluate-my-environment.md). O artigo[Avaliar meu ambiente](../3-envision-evaluate-my-environment.md) fornece informações adicionais sobre requisitos de largura de banda, proxy e firewall e também como testar sua rede usando a [Ferramenta de Avaliação de Rede](../3-envision-evaluate-my-environment.md#test-the-network).
