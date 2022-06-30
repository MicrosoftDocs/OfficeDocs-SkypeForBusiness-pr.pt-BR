---
title: Compatibilidade ambiental – Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: Como executar uma descoberta ambiental detalhada ao planejar sua jornada do Skype for Business para o Microsoft Teams.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 348a0e615f5ef876bfdd62b71adb30f6bf242dd6
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562600"
---
# <a name="environmental-discovery-for-a-microsoft-teams-rollout"></a>Descoberta ambiental para uma distribuição do Microsoft Teams

A descoberta é uma das primeiras etapas importantes que você executa ao planejar sua jornada para o Microsoft Teams.

Você executa uma descoberta detalhada do seu ambiente para entender melhor seu estado atual e revelar quaisquer dificuldades ou, ainda mais, possíveis bloqueadores para a execução da distribuição do Teams.

## <a name="discovery-questionnaire"></a>Questionário de descoberta

O questionário de exemplo abaixo orienta você em um conjunto de perguntas para confirmar que sua organização está pronta para a distribuição bem-sucedida de Audioconferência e Sistema de Telefonia com recursos de Planos de Chamadas no Teams.

Todos os assuntos relacionados à sua infraestrutura de colaboração existente e à organização do Microsoft 365 ou Office 365, rede, pontos de extremidade, operações e adoção e preparação são incluídos como parte do questionário de descoberta ambiental.

O questionário é dividido em várias seções para confirmar a preparação da sua organização para a implantação do Teams em várias áreas principais. Trabalhe com sua equipe de projeto para fornecer as informações solicitadas com o máximo de detalhes possível para facilitar suas atividades de planejamento.

> [!TIP]
> Você pode começar copiando o questionário para um documento do Microsoft Word. Tente responder a todas as perguntas e capturar todos os detalhes conforme você avança.

### <a name="project-team"></a>Equipe de projeto

Capture informações detalhadas sobre os principais stakeholders do seu projeto de distribuição do Teams. Observe que uma pessoa pode desempenhar várias funções em todo o projeto.

> | Função | Nome, endereço de email, número de telefone | Local, fuso horário | Comentários |
> |---|---|---|---|
> | Patrocinador executivo | | | |
> | Líder de projeto | | | |
> | Líder/arquiteto de colaboração | | | |
> | Consultor | | | |
> | Gerente de projetos | | | |
> | Especialista em adoção/gerenciamento de mudanças | | | |
> | Líder de rede | | | |
> | Líder de segurança | | | |
> | Líder de telefonia | | | |
> | Líder de desktop | | | |
> | Líder de suporte/suporte técnico | | | |
> | Líder de implantação | | | |
> | Proprietário do serviço | | | |
> | Líder de instalações | | | |
> | Líder da equipe de vídeo | | | |
> | Clientes potenciais de unidade de negócios | | | |

## <a name="microsoft-365-or-office-365-organization-details"></a>Detalhes da organização Office 365 Microsoft 365 ou Office 365

É altamente recomendável que você tenha uma organização ativa do Microsoft 365 ou Office 365 enquanto trabalha com este questionário. Se você ainda não ativou ou configurou uma organização do Microsoft 365 ou Office 365, confira Planejar sua configuração do [Microsoft 365 para empresas](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645).

Use a tabela a seguir para capturar informações sobre o Microsoft 365 ou Office 365 organização.

> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | Observe a produção do Microsoft 365<br/>ou Office 365 nome e ID da organização<br/>na coluna Resposta. Se você tiver mais<br/>do que um locatário associado a<br/>sua organização, anote todas as IDs. | Nome do Locatário: <br/>ID do locatário:| |
> | Em quais regiões os locatários são implantados?| | |
> | Observe o tipo desses Microsoft 365 ou <br/>Office 365 locatários. Eles são multilocatário <br/>ou Dedicado? | <input type="checkbox"> Multilocatário<br/> <input type="checkbox"> Dedicado | |
> | Quais produtos Microsoft Online estão em uso no momento? <br/>Observe o número de usuários habilitados para cada <br/>na coluna Comentários. | <input type="checkbox"> Microsoft Teams <br/> <input type="checkbox">Skype for Business <br/>&nbsp; &nbsp; &nbsp;Online <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox"> SharePoint Online <br/> <input type="checkbox">OneDrive for Business <br/> <input type="checkbox"> Yammer <br/> <input type="checkbox"> Outros| |
> | Qual nível de licença está habilitado para o Skype for <br/>Usuários do Business Online? | <input type="checkbox"> E1/G1 <br/> <input type="checkbox"> E2/G2 <br/> <input type="checkbox"> E3/G3 <br/> <input type="checkbox"> E4/G4 E5 | O número de usuários <br/>para cada SKU: |
> | Qual é a floresta atual do Active Directory <br/>nível funcional no ambiente? <br/>Se houver mais de uma floresta, observe os detalhes <br/>na coluna Comentários. | <input type="checkbox"> Windows Server 2000 <br/> <input type="checkbox"> Windows Server 2003 <br/> <input type="checkbox"> Windows Server 2008<br/> <input type="checkbox"> Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | O que você está usando para o diretório <br/>sincronização hoje? |<input type="checkbox"> Sem sincronização (somente nuvem) <br/> <input type="checkbox"> Azure Active Directory <br/>&nbsp;&nbsp; &nbsp; Conectar <br/> <input type="checkbox"> Outros (especifique no <br/>&nbsp;&nbsp; &nbsp; Coluna comentários.)| |
> | A identidade federada está implantada no momento? <br/>(Serviços de Federação do Active Directory (AD FS) ou <br/>de terceiros) | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |
> | Se você estiver usando a identidade federada, qual é a <br/>infraestrutura de federação? | <input type="checkbox"> Windows 2008 R2 AD FS <br/> <input type="checkbox"> Windows 2012 AD FS <br/> <input type="checkbox"> Windows 2012 R2 AD FS <br/> <input type="checkbox"> Windows 2016 AD FS <br/> <input type="checkbox"> Federação de terceiros <br/>&nbsp;&nbsp; &nbsp;gateway (observe os detalhes <br/>&nbsp;&nbsp; &nbsp;na coluna Comentários.) | |
> | Se você atualmente mantém um Microsoft 365 ativo<br/>ou Office 365 locatário, é o domínio SMTP/SIP de <br/>seus usuários de destino associados ao locatário? | <input type="checkbox"> N/A – Nenhum Microsoft 365 ou<br/>&nbsp;&nbsp; &nbsp;Office 365 locatário in-loco <br/> <input type="checkbox"> Não, SMTP/SIP dos usuários <br/>&nbsp;&nbsp; &nbsp;o domínio não está associado <br/>&nbsp;&nbsp; &nbsp;com todos os locatários em <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 ou Office 365<br/> <input type="checkbox"> Sim, SMTP/SIP dos usuários <br/>&nbsp;&nbsp; &nbsp;o domínio está associado <br/>&nbsp;&nbsp; &nbsp;com um locatário existente no <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 ou Office 365 | |
> | Os UPNs do usuário correspondem ao endereço SMTP primário? | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não <br/> <input type="checkbox"> Inconsistentemente | |

## <a name="existing-collaboration-platform-summary"></a>Resumo da plataforma de colaboração existente

Use a tabela a seguir para capturar informações sobre sua implantação de plataforma de colaboração existente.

> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | O Microsoft Teams está implantado? | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |
> | O Skype for Business está implantado? <br/>Para implantações locais e híbridas, verifique se <br/>você observa a versão e a CU (atualização cumulativa) <br/>detalhes na coluna Comentários. | <input type="checkbox"> Sim, Microsoft 365 ou <br/>&nbsp; &nbsp; &nbsp;Office 365 <br/> <input type="checkbox"> Sim, híbrido (com <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 ou <br/>&nbsp;&nbsp; &nbsp;Office 365) <br/> <input type="checkbox"> Sim, local <br/> <input type="checkbox"> Sim, online, dedicado <br/>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox"> Sim, hospedado, dedicado <br/>&nbsp;&nbsp; &nbsp;(terceiros) <br/> <input type="checkbox"> Sim, hospedado, compartilhado <br/>&nbsp;&nbsp; &nbsp;(terceiros) <br/> <input type="checkbox"> Não, outros | |
> | O Exchange está implantado? <br/>Para implantações locais e híbridas, verifique se <br/>você observa a versão e os detalhes da CU nos Comentários <br/>Coluna. | <input type="checkbox"> Sim, Microsoft 365 <br/> <input type="checkbox"> Sim, híbrido (com <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 ou <br/>&nbsp;&nbsp; &nbsp;Office 365) <br/> <input type="checkbox"> Sim, local <br/> <input type="checkbox"> Sim, online, dedicado <br/>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox"> Sim, hospedado, dedicado <br/>&nbsp;&nbsp; &nbsp;(terceiros) <br/> <input type="checkbox"> Sim, hospedado, compartilhado <br/>&nbsp;&nbsp; &nbsp;(terceiros) <br/> <input type="checkbox"> Não, outros | |
> | O SharePoint está implantado? <br/>Para implantações locais e híbridas, verifique se <br/>você observa a versão e os detalhes da CU nos Comentários <br/>Coluna. | <input type="checkbox"> Sim, Microsoft 365 <br/> <input type="checkbox"> Sim, híbrido (com <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 ou <br/>&nbsp;&nbsp; &nbsp;Office 365) <br/> <input type="checkbox"> Sim, local <br/> <input type="checkbox"> Sim, online, dedicado <br/>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox"> Sim, hospedado, dedicado <br/>&nbsp;&nbsp; &nbsp;(terceiros) <br/> <input type="checkbox"> Sim, hospedado, compartilhado <br/>&nbsp;&nbsp; &nbsp;(terceiros) <br/> <input type="checkbox"> Não, outros | |
> | A OneDrive for Business implantada? | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |
> | Você tem outras plataformas de terceiros implantadas <br/>e em uso hoje? Nesse caso, observe o número de usuários de <br/>essas plataformas e os detalhes de uso no <br/>Coluna de comentários. | <input type="checkbox"> Cisco Webex <br/> <input type="checkbox"> Folga <br/> <input type="checkbox"> Outros (especifique no <br/>&nbsp;&nbsp; &nbsp; Coluna comentários.) | Número de usuários: <br/>Detalhes:|
> | Você está planejando mover usuários desses terceiros <br/>plataformas para o Teams? | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |
> | Qual é a solução de telefonia e conferência atual <br/>dos usuários que estão no escopo dessa iniciativa? | | |
> | Você tem [SBC que dão suporte ao Roteamento Direto](./direct-routing-plan.md#supported-session-border-controllers-sbcs) implantado <br/>para seus escritórios que estão no escopo dessa iniciativa? Se Sim,<br/>observe os detalhes na coluna Comentários.| <input type="checkbox"> Sim <br/> <input type="checkbox"> Não ||

## <a name="collaboration-platform-deployment-details"></a>Detalhes de implantação da plataforma de colaboração

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (se aplicável)

Se aplicável, capture os detalhes da implantação do Teams usando a tabela de exemplo abaixo. Se você ainda não implantou o Teams, ignore esta seção.

> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | Que tipos de usuários estão habilitados para o Microsoft Teams? | <input type="checkbox"> Todos os usuários na organização <br/> <input type="checkbox"> Usuários/grupos de usuários específicos <br/>&nbsp;&nbsp; &nbsp;(Especifique na coluna Comentários.) ||
> | Quais recursos e modalidades do Teams estão em uso? | <input type="checkbox"> Conversas baseadas em canal <br/> <input type="checkbox"> Chat privado <br/> <input type="checkbox"> Acesso de convidado <br/> <input type="checkbox"> Reuniões de canal <br/> <input type="checkbox"> Reuniões particulares <br/> <input type="checkbox"> Chamada privada <br/> <input type="checkbox"> Reunião de canal ad hoc <br/> <input type="checkbox"> Vídeos em reuniões <br/> <input type="checkbox"> Compartilhamento de tela em reuniões <br/> <input type="checkbox"> Audioconferência <br/><input type="checkbox"> Aplicativos (aplicativos)<br/> &nbsp;&nbsp; &nbsp;<input type="checkbox"> Guias<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Bots <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Conectores<br/><input type="checkbox"> Integração de armazenamento em nuvem personalizada <br/>&nbsp;&nbsp; &nbsp; Dropbox, Box, ShareFile, Google <br/>&nbsp;&nbsp; &nbsp; Drive, Egnyte <br/> <input type="checkbox"> Integração de email de canal <br/> <input type="checkbox"> Outros (especifique na coluna Comentários.) | |
> | Quais aplicativos você implantou no Teams? | | |
> | Você bloqueou especificamente alguma funcionalidade do Microsoft Teams? <br/>Se Sim, anote os detalhes na coluna Comentários. | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não ||
> | Quais clientes Microsoft Teams estão em uso? | <input type="checkbox"> Web <br/> <input type="checkbox"> Windows <br/> <input type="checkbox"> Mac <br/> <input type="checkbox"> Linux <br/>  <input type="checkbox"> Ios <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> Windows Mobile | |
> | Quem tem permissões para criar equipes? | <input type="checkbox"> Todos na organização <br/>&nbsp;&nbsp; &nbsp;(Essa é a configuração padrão) <br/> <input type="checkbox"> Pessoas específicas <br/>&nbsp;&nbsp; &nbsp;(Especifique na coluna Comentários.) | |
> | Você está usando os recursos de segurança e conformidade do Microsoft Teams? | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |

### <a name="skype-for-business-online-if-applicable"></a>Skype for Business Online (se aplicável)

Se aplicável, capture os detalhes da implantação Skype for Business Online usando a tabela de exemplo abaixo. Se você ainda não implantou a Skype for Business Online, ignore esta seção.

> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | Quais tipos de usuários estão habilitados para o Skype <br/>para o Business Online? | <input type="checkbox"> Todos os usuários na organização <br/> <input type="checkbox"> Usuários/grupos de usuários específicos <br/>&nbsp;&nbsp; &nbsp;(Especifique na coluna Comentários.) | |
> | Quais modalidades e recursos estão atualmente <br/>em uso hoje? | <input type="checkbox"> Mensagens Instantâneas e Presença (IM/P)<br/> <input type="checkbox"> Conferência <br/> <input type="checkbox"> Federação <br/> <input type="checkbox"> Gravação de Reunião <br/> <input type="checkbox"> Audioconferência da Microsoft <br/> <input type="checkbox"> Audioconferência de terceiros (Observação<br/>&nbsp;&nbsp; &nbsp;os detalhes na coluna Comentários.) <br/> <input type="checkbox"> Planos de Chamadas (anteriormente chamada PSTN) <br/> <input type="checkbox"> Atendedores Automáticos Organizacionais <br/> <input type="checkbox"> Filas de Chamadas | |
> | Você bloqueou especificamente qualquer Skype for <br/>Funcionalidades do Business Online? <br/>Se Sim, anote os detalhes na coluna Comentários. | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |
> | Qual método você está usando ou planeja usar para <br/>conectar o Sistema de Telefonia (antigo Cloud PBX) ao <br/>O PSTN? <br/>Selecione todos os que se aplicam. | <input type="checkbox"> Planos de Chamadas (anteriormente chamada PSTN) <br/> <input type="checkbox"> Conectividade PSTN local <br/>&nbsp;&nbsp; &nbsp;(aproveitando o Skype for existente <br/>&nbsp;&nbsp; &nbsp; Business 2015 ou Lync Server <br/>&nbsp;&nbsp; &nbsp;Implantação de 2013) <br/> <input type="checkbox"> Conectividade PSTN local <br/>&nbsp;&nbsp; &nbsp;(usando o Cloud Connector) | |
> | Você fez a portabilidade de algum número de telefone para a Microsoft? <br/>Isso é aplicável a Planos de Chamadas e Áudio <br/>Recursos de conferência. | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype for Business local (se aplicável)

Se aplicável, capture os detalhes da implantação Skype for Business usando a tabela de exemplo abaixo. Se você ainda não implantou Skype for Business local, ignore esta seção.

> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | Quais versões do Lync ou Skype for Business <br/> atualmente são implantados localmente? | <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">Skype for Business Server 2015 <br/> <input type="checkbox">Skype for Business Server 2019 <br/><input type="checkbox">Skype for Business Cloud Connector <br/>&nbsp;&nbsp; &nbsp; Edição | |
> | A implantação híbrida o Skype for Business Online está configurada? | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |
> | Esse ambiente é hospedado e gerenciado por um terceiro <br/>Festa? Se Sim, observe os detalhes no <br/>Coluna de comentários. | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |
> | Quais modalidades e recursos estão em uso no momento <br/>Hoje? | <input type="checkbox"> Mensagens Instantâneas e Presença (IM/P) <br/> <input type="checkbox"> Conferência <br/> <input type="checkbox"> Federação <br/> <input type="checkbox"> Gravação de Reunião <br/> <input type="checkbox"> Chat Persistente/Chat em Grupo <br/> <input type="checkbox"> Audioconferência da Microsoft <br/>&nbsp;&nbsp; &nbsp;(anteriormente discada em conferência) em seu <br/>&nbsp;&nbsp; &nbsp;Lync Server local ou <br/>&nbsp;&nbsp; &nbsp;Skype for Business implantação <br/> <input type="checkbox"> Audioconferência de terceiros <br/>&nbsp;&nbsp; &nbsp;(Observe os detalhes nos Comentários <br/>&nbsp;&nbsp; &nbsp;column.) <br/> <input type="checkbox">Enterprise Voice usando o local <br/>&nbsp; &nbsp; &nbsp;Conectividade PSTN <br/> <input type="checkbox"> Planos de Chamadas (anteriormente chamada PSTN) via <br/>&nbsp;&nbsp; &nbsp; Híbrido com Skype for Business Online | |
> | Quais versões do Servidor de Borda você tem implantadas? | <input type="checkbox"> Office Communications Server 2007 "R1" <br/> <input type="checkbox"> Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">Skype for Business Server 2015 <br/> <input type="checkbox">Skype for Business Server 2019| |
> | Você tem o Lync ou o Skype for Business Edge <br/>implantado em mais de um datacenter? <br/>Se Sim, anote os detalhes na coluna Comentários. | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |
> | Selecione os serviços que sua função de Borda fornece hoje. | <input type="checkbox"> Acesso de usuário externo (usuários corporativos) <br/> <input type="checkbox"> Acesso de usuário remoto (anônimo <br/>&nbsp;&nbsp; &nbsp;participantes externos da reunião) <br/> <input type="checkbox"> Federação <br/> <input type="checkbox"> Retransmissão de mídia | |
> | Qual dos seguintes recursos de chamada de voz você <br/>atualmente tem dependências? <br/>Anote as dependências adicionais nos Comentários <br/>Coluna. | <input type="checkbox"> Opções de disponibilidade <br/> <input type="checkbox"> Estacionamento de chamada <br/> <input type="checkbox"> Recebimento de chamadas ou recebimento de chamadas em grupo <br/> <input type="checkbox"> Telefones de área comum ou "mesa quente" <br/> <input type="checkbox"> Grupos de resposta ou grupos de busca <br/> <input type="checkbox"> Aparência de linha compartilhada <br/> <input type="checkbox"> Linha privada <br/> <input type="checkbox"> Voicemail <br/> <input type="checkbox"> Chamada via trabalho <br/> <input type="checkbox"> Números de emergência ou informações <br/>&nbsp;&nbsp; &nbsp;(911, 811, 411) <br/> <input type="checkbox"> Discagem de extensão <br/> <input type="checkbox"> Atendedor Automático <br/> <input type="checkbox"> Acesso de assinante <br/> <input type="checkbox"> Dispositivos analógicos <br/> <input type="checkbox"> Fax <br/> <input type="checkbox"> Mascaramento ou alteração da ID do chamador <br/> <input type="checkbox"> Roteamento baseado em localização <br/> <input type="checkbox"> Roteamento de menor custo <br/> <input type="checkbox"> Telefones de elevador | |

## <a name="networking-and-access-to-microsoft-365-and-office-365-services"></a>Rede e acesso aos serviços microsoft 365 e Office 365

Use a tabela a seguir para capturar os detalhes de rede da sua organização e como os usuários estão (ou serão) conectados aos serviços microsoft 365 e Office 365.

> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | Como fazer (ou como) os usuários no escopo da migração <br/>acessar o Teams quando eles estiverem no escritório? <br/>Selecione todos os que se aplicam. | <input type="checkbox"> Conexão NAT roteada <br/> <input type="checkbox"> Servidor proxy <br/> <input type="checkbox"> Público Wi-Fi <br/> <input type="checkbox"> Gerenciamento (não público) Wi-Fi <br/> <input type="checkbox"> ExpressRoute <br/>&nbsp;&nbsp; &nbsp;(Emparelhamento da Microsoft) ||
> | Se o acesso ao Microsoft 365 ou Office 365 for por meio de um<br/>servidor proxy, há alguma maneira de ignorar o proxy? | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |
> | A Rota Expressa está sendo usada atualmente? | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não <br/> <input type="checkbox"> Não, mas está sendo planejado. | |
> | Você executou uma Avaliação de Preparação de Rede? | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |
> | Os usuários precisam usar uma VPN ao se conectar a <br/>recursos corporativos remotamente? | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |
> | Se uma VPN for usada, o tráfego do Teams poderá ser excluído <br/>a VPN para acessar o Microsoft 365 e Office 365 Services diretamente? | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |
> | Sua rede dá suporte a QoS? | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |
> | Você pode priorizar o tráfego de áudio e vídeo do Teams <br/>para impulsionar uma experiência de alta qualidade? | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |
> | Todos os locais dentro de uma região têm saída da Internet, <br/>ou a saída da Internet está centralizada para toda a região? | <input type="checkbox"> Acesso regional à Internet <br/> <input type="checkbox"> Acesso centralizado ao <br/>&nbsp;&nbsp; &nbsp;Internet | |

## <a name="endpoints"></a>Pontos de extremidade

Use a tabela a seguir para capturar os detalhes dos clientes e pontos de extremidade em uso.

> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | Que sistema operacional de área de trabalho os usuários estão utilizando? | <input type="checkbox"> Windows XP <br/> <input type="checkbox"> Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox"> Mac (especifique a versão na coluna Comentários.) <br/> <input type="checkbox"> Linux (especifique a distribuição na coluna Comentários.) <br/><input type="checkbox"> Outros (Observe os detalhes na coluna Comentários.) | |
> | Qual versão do Microsoft Office está implantada <br/>para esses dispositivos? | <input type="checkbox"> Office 2003 <br/> <input type="checkbox"> Office 2007 <br/> <input type="checkbox"> Office 2010 <br/> <input type="checkbox"> Office 2013 <br/> <input type="checkbox"> Office 2016 <br/> <input type="checkbox">Office para Mac 2011 <br/> <input type="checkbox">Office para Mac 2016 <br/> <input type="checkbox"> Outros (Observe os detalhes na coluna Comentários.) | |
> | Qual tecnologia de implantação do Office está em uso <br/>em sua organização? | <input type="checkbox"> MSI <br/> <input type="checkbox"> Clique para Executar | |
> | Quais são os dispositivos móveis permitidos e com suporte <br/>plataformas em uso? <br/>Selecione todos os que se aplicam. | <input type="checkbox"> Windows <br/> <input type="checkbox"> Móvel <br/> <input type="checkbox"> Ios <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> Outros (Observe os detalhes na coluna Comentários.) | |
> | Como os dispositivos móveis são fornecidos? <br/>Selecione todos os que se aplicam. | <input type="checkbox"> Dispositivos corporativos <br/> <input type="checkbox"> Traga seu próprio dispositivo | |
> | Quais dispositivos os usuários usam atualmente para acessar <br/>serviços de voz e conferência <br/>(fones de ouvido, fones de ouvido, telefones, vídeo)? | | |

## <a name="operations"></a>Operações

Use a tabela a seguir para capturar os detalhes dos aspectos operacionais do seu ambiente.

> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | Qual é o seu modelo de operações para o Lync Server, <br/>Skype for Business Server, implantação do Microsoft 365, <br/>ou Office 365 implantação hoje? | | |
> | Você pode descrever a organização de suporte atual para <br/>Lync Server, Skype for Business Server, Microsoft 365, <br/>ou Office 365? | | |
> | Se você estiver implantando em vários países ou regiões, <br/>cada país/região tem sua própria TI/telefonia <br/>equipe para trabalhar ou isso será gerenciado centralmente? | <input type="checkbox"> Operações e suporte regionais <br/> <input type="checkbox"> Operações e suporte centralizados | |
> | Você está acompanhando a Metodologia de Qualidade da Chamada? | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |
> | Você atribuiu um indivíduo ou equipe ao <br/>Função Defensor da Qualidade para a plataforma de colaboração <br/>em uso? | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não ||
> | Como monitorar o Lync Server, Skype for <br/>Business Server, implantação do Microsoft 365 ou <br/>Office 365 implantação? | | |
> | Você tem problemas de qualidade das chamadas? | <input type="checkbox"> Sim<br/> <input type="checkbox"> Não | |
> | Como e quando você fornece treinamento para seu <br/>suporte técnico em novos serviços e funcionalidades? | | |

## <a name="adoption-and-readiness"></a>Adoção e preparação

Use a tabela a seguir e registre o estado atual de adoção e preparação de sua organização.

>
> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | Qual é o uso ativo atual de <br/>Skype for Business? | **__** % total de usuários ativos versus usuários habilitados | |
> | Como sua organização está usando <br/>Skype for Business? | Conversas privadas <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> IM <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Chamar <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Compartilhar<br/> Reuniões <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Conferência<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Compartilhar<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Chamar | |
> | Sua organização tem uma adoção do usuário <br/>e equipe de Gerenciamento de Alterações? | <input type="checkbox"> Sim<br/> <input type="checkbox"> Não | |
> | Como você mede o sucesso da tecnologia no momento <br/>distribuição como Skype for Business? | | |
> | Qual percentual de sua base de usuários você diria que tem <br/>adotado Skype for Business? | | |
> | Qual é a opinião dos usuários a respeito do Skype for Business? | <input type="checkbox"> Bom <br/> <input type="checkbox"> Neutro <br/> <input type="checkbox"> Ruim | |
> | Qual das opções a seguir descreve melhor a distribuição <br/>estratégia usada para sua Skype for Business <br/>Implantação? | <input type="checkbox"> Alcance amplo: campanha de email com <br/>&nbsp;&nbsp; &nbsp;links para treinamento <br/> <input type="checkbox"> Expandido: alcance amplo mais uma variedade <br/>&nbsp;&nbsp; &nbsp;campanhas de conscientização (cartazes, <br/>&nbsp;&nbsp; &nbsp;eventos, campeões) e treinamento <br/>&nbsp;&nbsp; &nbsp;(vídeos, guias do usuário, pessoalmente) <br/> <input type="checkbox"> Personalizado: expandido, mais direcionado <br/>&nbsp;&nbsp; &nbsp;mensagens e treinamento por persona <br/> <input type="checkbox"> Outros <br/>&nbsp;&nbsp; &nbsp;(Observe os detalhes na coluna Comentários.) | |
