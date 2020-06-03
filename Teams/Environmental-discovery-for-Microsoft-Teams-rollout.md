---
title: Compatibilidade ambiental-Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: Como realizar uma descoberta ambiental detalhada enquanto planeja sua jornada do Skype for Business para o Microsoft Teams.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6decfba208fd33bfd1326b4839ef77c9fc1f7558
ms.sourcegitcommit: 6acede580649588334aeb48130ab2a5d73245723
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2020
ms.locfileid: "44522674"
---
<a name="environmental-discovery-for-a-microsoft-teams-rollout"></a>Descoberta ambiental para uma implementação do Microsoft Teams
===================================================

A descoberta é uma das principais etapas que você faz ao planejar sua jornada para o Microsoft Teams.

Você executa uma descoberta detalhada do seu ambiente para compreender melhor seu estado atual e para revelar qualquer dificuldade ou, ainda mais, os bloqueadores para a execução de sua distribuição de suas equipes.

## <a name="discovery-questionnaire"></a>Questionário de descoberta

O questionário de exemplo a seguir orienta você por um conjunto de perguntas para confirmar se a sua organização está pronta para a distribuição bem-sucedida da conferência de áudio e do sistema telefônico com recursos de planos de chamada no Teams.

Todas as questões relacionadas à sua infraestrutura de colaboração existente e à Microsoft 365 ou à organização do Office 365, à rede, aos pontos de extremidade, às operações e à preparação e à preparação são incluídas como parte do questionário de descoberta ambiental.

O questionário é dividido em várias seções para confirmar a preparação da sua organização para a implantação de suas equipes em várias áreas principais. Trabalhe com sua equipe de projeto para fornecer as informações solicitadas com o máximo de detalhes possível para facilitar suas atividades de planejamento.

> [!TIP]
> Você pode começar copiando o questionário em um documento do Microsoft Word. Tente responder a todas as perguntas e capturar todos os detalhes durante a mudança.

<a name="project-team"></a>Equipe do projeto
---

Capture informações detalhadas sobre os principais participantes do projeto de distribuição de suas equipes. Observe que uma pessoa pode executar várias funções em todo o projeto.

> | Função | Nome, endereço de e-mail, número de telefone | Local, fuso horário | Comentários |
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
> | Leads unitários comerciais | | | |

<a name="microsoft-365-or-office-365-organization-details"></a>Detalhes da organização do Microsoft 365 ou do Office 365
---

É altamente recomendável que você tenha uma organização ativa do Microsoft 365 ou do Office 365 enquanto trabalha com este questionário. Se você ainda não ativou ou configurou uma organização do Microsoft 365 ou do Office 365, consulte [planejar a configuração do microsoft 365 para empresas](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645).

Use a tabela a seguir para capturar informações sobre a organização do Microsoft 365 ou do Office 365.

> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | Observe a produção Microsoft 365<br/>ou o nome e a ID da organização do Office 365<br/>na coluna resposta. Se você tiver mais<br/>de um locatário associado a<br/>sua organização, anote todas as IDs. | Nome do locatário: <br/>ID do locatário:| |
> | Em quais regiões os locatários foram implantados?| | |
> | Observe o tipo de estes Microsoft 365 ou <br/>Locatários do Office 365. São multilocatários <br/>ou dedicado? | <input type="checkbox">Multilocatário<br/> <input type="checkbox">Dedicar | |
> | Quais produtos Microsoft Online estão em uso no momento? <br/>Observe o número de usuários habilitados para cada <br/>serviço na coluna comentários. | <input type="checkbox">Microsoft Teams <br/> <input type="checkbox">Skype for Business <br/>&nbsp; &nbsp; &nbsp;Online <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox">SharePoint Online <br/> <input type="checkbox">OneDrive for Business <br/> <input type="checkbox">Yammer <br/> <input type="checkbox">Demais| |
> | Qual nível de licença está habilitado para o Skype para <br/>Usuários do Business Online? | <input type="checkbox">E1/G1 <br/> <input type="checkbox">E2/G2 <br/> <input type="checkbox">E3/G3 <br/> <input type="checkbox">E4/G4 E5 | O número de usuários <br/>para cada SKU: |
> | O que é a floresta atual do Active Directory <br/>nível funcional no ambiente? <br/>Se houver mais de uma floresta, observe os detalhes <br/>na coluna comentários. | <input type="checkbox">Windows Server 2000 <br/> <input type="checkbox">Windows Server 2003 <br/> <input type="checkbox">Windows Server 2008<br/> <input type="checkbox">Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | O que você está usando para o diretório <br/>sincronização hoje? |<input type="checkbox">Sem sincronização (somente na nuvem) <br/> <input type="checkbox">Active Directory do Azure <br/>&nbsp;&nbsp; &nbsp; Conectado <br/> <input type="checkbox">Outro (especificar na <br/>&nbsp;&nbsp; &nbsp; Coluna comentários.)| |
> | A identidade federada está implantada no momento? <br/>(Serviços de Federação do Active Directory ou <br/>terceiros) | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Se você estiver usando identidade federada, qual é o <br/>infraestrutura de Federação? | <input type="checkbox">Windows 2008 R2 AD FS <br/> <input type="checkbox">Windows 2012 AD FS <br/> <input type="checkbox">Windows 2012 R2 AD FS <br/> <input type="checkbox">Windows 2016 AD FS <br/> <input type="checkbox">Federação de terceiros <br/>&nbsp;&nbsp; &nbsp; Gateway (Observe os detalhes <br/>&nbsp;&nbsp; &nbsp; na coluna comentários.) | |
> | Se você atualmente mantém um Microsoft 365 ativo<br/>ou o locatário do Office 365 é o domínio SMTP/SIP do <br/>seus usuários de destino associados ao locatário? | <input type="checkbox">N/d – sem Microsoft 365 ou<br/>&nbsp;&nbsp; &nbsp; Locatário do Office 365 no local <br/> <input type="checkbox">Não, SMTP/SIP dos usuários <br/>&nbsp;o &nbsp; &nbsp; domínio não está associado <br/>&nbsp;&nbsp; &nbsp; com qualquer locatário em <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 ou Office 365<br/> <input type="checkbox">Sim, SMTP/SIP dos usuários <br/>&nbsp;&nbsp; &nbsp; domínio está associado <br/>&nbsp;&nbsp; &nbsp; com um locatário existente no <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 ou Office 365 | |
> | Os UPNs do usuário correspondem ao endereço SMTP principal? | <input type="checkbox">Sim <br/> <input type="checkbox">Não <br/> <input type="checkbox">Está inconsistente | |

<a name="existing-collaboration-platform-summary"></a>Resumo da plataforma de colaboração existente
---

Use a tabela a seguir para capturar informações sobre a implantação da plataforma de colaboração existente.

> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | O Microsoft Teams está implantado? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | O Skype for Business está implantado? <br/>Para implantações locais e híbridas, certifique-se de que <br/>Você anota a versão e a atualização cumulativa (RECOR) <br/>detalhes na coluna comentários. | <input type="checkbox">Sim, Microsoft 365 ou <br/>&nbsp; &nbsp; &nbsp;Office 365 <br/> <input type="checkbox">Sim, híbrido (com <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 ou <br/>&nbsp;&nbsp; &nbsp; Office 365) <br/> <input type="checkbox">Sim, local <br/> <input type="checkbox">Sim, online, dedicada <br/>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox">Sim, hospedado, dedicado <br/>&nbsp;&nbsp; &nbsp; (terceiros) <br/> <input type="checkbox">Sim, hospedado, compartilhado <br/>&nbsp;&nbsp; &nbsp; (terceiros) <br/> <input type="checkbox">Não, outros | |
> | O Exchange está implantado? <br/>Para implantações locais e híbridas, certifique-se de que <br/>Você anota a versão e a RECOR detalhes nos comentários <br/>coluna. | <input type="checkbox">Sim, Microsoft 365 <br/> <input type="checkbox">Sim, híbrido (com <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 ou <br/>&nbsp;&nbsp; &nbsp; Office 365) <br/> <input type="checkbox">Sim, local <br/> <input type="checkbox">Sim, online, dedicada <br/>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox">Sim, hospedado, dedicado <br/>&nbsp;&nbsp; &nbsp; (terceiros) <br/> <input type="checkbox">Sim, hospedado, compartilhado <br/>&nbsp;&nbsp; &nbsp; (terceiros) <br/> <input type="checkbox">Não, outros | |
> | O SharePoint está implantado? <br/>Para implantações locais e híbridas, certifique-se de que <br/>Você anota a versão e a RECOR detalhes nos comentários <br/>coluna. | <input type="checkbox">Sim, Microsoft 365 <br/> <input type="checkbox">Sim, híbrido (com <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 ou <br/>&nbsp;&nbsp; &nbsp; Office 365) <br/> <input type="checkbox">Sim, local <br/> <input type="checkbox">Sim, online, dedicada <br/>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox">Sim, hospedado, dedicado <br/>&nbsp;&nbsp; &nbsp; (terceiros) <br/> <input type="checkbox">Sim, hospedado, compartilhado <br/>&nbsp;&nbsp; &nbsp; (terceiros) <br/> <input type="checkbox">Não, outros | |
> | O OneDrive for Business está implantado? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Você tem outros plataformas de terceiros implantadas <br/>e em uso hoje? Em caso afirmativo, anote o número de usuários do <br/>essas plataformas e os detalhes de uso no <br/>Coluna de comentários. | <input type="checkbox">Cisco WebEx <br/> <input type="checkbox">Desperdiça <br/> <input type="checkbox">Outro (especificar na <br/>&nbsp;&nbsp; &nbsp; Coluna comentários.) | Número de usuários: <br/>Os|
> | Você pretende mover os usuários dessas pessoas de terceiros <br/>plataformas para o Teams? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | O que é a solução de telefonia e conferência atual <br/>dos usuários que estão no escopo dessa iniciativa? | | |
> | Você tem [SBC que dão suporte ao roteamento direto](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) implantado <br/>para seus escritórios que têm escopo para esta iniciativa? Se sim,<br/>Observe os detalhes na coluna comentários.| <input type="checkbox">Sim <br/> <input type="checkbox">Não ||

<a name="collaboration-platform-deployment-details"></a>Detalhes da implantação da plataforma de colaboração
---

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (se aplicável)

Se aplicável, capture os detalhes de sua implantação de equipes usando a tabela de exemplo abaixo. Se você ainda não implantou o Microsoft Teams, pule esta seção.

> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | Que tipos de usuários estão habilitados para o Microsoft Teams? | <input type="checkbox">Todos os usuários da organização <br/> <input type="checkbox">Usuários/grupos de usuários específicos <br/>&nbsp;&nbsp; &nbsp; (Especificar na coluna comentários.) ||
> | Quais recursos e modalidades de equipe estão em uso? | <input type="checkbox">Conversas baseadas em canais <br/> <input type="checkbox">Chat privado <br/> <input type="checkbox">Acesso de convidado <br/> <input type="checkbox">Reuniões de canal <br/> <input type="checkbox">Reuniões privadas <br/> <input type="checkbox">Chamadas privadas <br/> <input type="checkbox">Canal ad-hoc Meetup <br/> <input type="checkbox">Vídeos em reuniões <br/> <input type="checkbox">Compartilhamento de tela em reuniões <br/> <input type="checkbox">Conferência de áudio <br/><input type="checkbox">Aplicativos (aplicativos)<br/> &nbsp;&nbsp; &nbsp;<input type="checkbox"> Efetua<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Bots <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Alinha<br/><input type="checkbox">Integração personalizada do armazenamento em nuvem <br/>&nbsp;&nbsp; &nbsp; Dropbox, Box, Sharefile, Google <br/>&nbsp;&nbsp; &nbsp; Unidade, Egnyte (disponível em breve) <br/> <input type="checkbox">Integração de email de canal <br/> <input type="checkbox">Outro (especificar na coluna comentários.) | |
> | Quais aplicativos você implantou para o Microsoft Teams? | | |
> | Você bloqueou especificamente alguma funcionalidade do Microsoft Teams? <br/>Em caso afirmativo, observe os detalhes na coluna comentários. | <input type="checkbox">Sim <br/> <input type="checkbox">Não ||
> | Quais clientes Microsoft Teams estão em uso? | <input type="checkbox">Pela <br/> <input type="checkbox">Windows <br/> <input type="checkbox">Macintosh <br/> <input type="checkbox">Linux <br/>  <input type="checkbox">SS <br/> <input type="checkbox">Android <br/> <input type="checkbox">Windows Mobile | |
> | Quem tem permissões para criar equipes? | <input type="checkbox">Todos na organização <br/>&nbsp;&nbsp; &nbsp; (Essa é a configuração padrão) <br/> <input type="checkbox">Pessoas específicas <br/>&nbsp;&nbsp; &nbsp; (Especificar na coluna comentários.) | |
> | Você está usando os recursos de segurança e conformidade do Microsoft Teams? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |

### <a name="skype-for-business-online-if-applicable"></a>Skype for Business Online (se aplicável)

Se aplicável, capture os detalhes da sua implantação do Skype for Business online usando a tabela de exemplo abaixo. Se você ainda não implantou a implantação do Skype for Business Online, pule esta seção.

> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | Que tipos de usuários estão habilitados para o Skype <br/>para negócios online? | <input type="checkbox">Todos os usuários da organização <br/> <input type="checkbox">Usuários/grupos de usuários específicos <br/>&nbsp;&nbsp; &nbsp; (Especificar na coluna comentários.) | |
> | Quais recursos e modalidades estão no momento <br/>em uso hoje? | <input type="checkbox">Mensagens instantâneas e presença (IM/P)<br/> <input type="checkbox">Conferência <br/> <input type="checkbox">Federação <br/> <input type="checkbox">Gravação de reunião <br/> <input type="checkbox">Conferência de áudio da Microsoft <br/> <input type="checkbox">Audioconferência (nota) de áudio de terceiros (Observação<br/>&nbsp;&nbsp; &nbsp; os detalhes na coluna comentários.) <br/> <input type="checkbox">Planos de chamada (antigo chamada PSTN) <br/> <input type="checkbox">Atendedores automáticos organizacionais <br/> <input type="checkbox">Filas de chamadas | |
> | Você bloqueou especificamente qualquer Skype para <br/>Recursos comerciais online? <br/>Em caso afirmativo, observe os detalhes na coluna comentários. | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Qual método você está usando ou planeja usar para <br/>conectar o sistema telefônico (anteriormente Cloud PBX) a <br/>a PSTN? <br/>Selecione todas as opções que se aplicam. | <input type="checkbox">Planos de chamada (antigo chamada PSTN) <br/> <input type="checkbox">Conectividade PSTN local <br/>&nbsp;&nbsp; &nbsp; (aproveitando o Skype existente para <br/>&nbsp;&nbsp; &nbsp; Business 2015 ou Lync Server <br/>&nbsp;&nbsp; &nbsp; implantação do 2013) <br/> <input type="checkbox">Conectividade PSTN local <br/>&nbsp;&nbsp; &nbsp; (usando o Cloud Connector) | |
> | Você fez a portabilidade de algum número de telefone para a Microsoft? <br/>Isso se aplica a planos de chamada e áudio <br/>Recursos de conferência. | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype for Business local (se aplicável)

Se aplicável, capture os detalhes da sua implantação do Skype for Business usando a tabela de exemplo abaixo. Se você ainda não implantou o Skype for Business local, pule esta seção.

> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | Quais versões do Lync ou Skype for Business <br/> Atualmente são implantados no local? | <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype for Business Server 2015 <br/> <input type="checkbox">Skype for Business Server 2019 <br/><input type="checkbox">Conector de nuvem do Skype for Business <br/>&nbsp;&nbsp; &nbsp; Edições | |
> | A implantação híbrida o Skype for Business Online está configurada? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Esse ambiente é hospedado e gerenciado por um terceiro <br/>terceiro? Em caso afirmativo, observe os detalhes na <br/>Coluna de comentários. | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Quais recursos e modalidades estão em uso no momento <br/>anunciou? | <input type="checkbox">Mensagens instantâneas e presença (IM/P) <br/> <input type="checkbox">Conferência <br/> <input type="checkbox">Federação <br/> <input type="checkbox">Gravação de reunião <br/> <input type="checkbox">Chat em grupo/chat persistente <br/> <input type="checkbox">Conferência de áudio da Microsoft <br/>&nbsp;&nbsp; &nbsp; (anteriormente discagem em conferência) em seu <br/>&nbsp;&nbsp; &nbsp; Lync Server local ou <br/>&nbsp;&nbsp; &nbsp; Implantação do Skype for Business <br/> <input type="checkbox">Conferência de áudio de terceiros <br/>&nbsp;&nbsp; &nbsp; (Observe os detalhes nos comentários <br/>&nbsp;&nbsp; &nbsp; coluna.) <br/> <input type="checkbox">Enterprise Voice usando o local <br/>&nbsp; &nbsp; &nbsp;Conectividade PSTN <br/> <input type="checkbox">Planos de chamada (antes chamadas PSTN) via <br/>&nbsp;&nbsp; &nbsp; Híbrido com o Skype for Business Online | |
> | Quais versões do Servidor de Borda você tem implantadas? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype for Business Server 2015 <br/> <input type="checkbox">Skype for Business Server 2019| |
> | Você tem o Lync ou o Skype for Business Edge <br/>implantado em mais de um datacenter? <br/>Em caso afirmativo, observe os detalhes na coluna comentários. | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Selecione os serviços que a sua função de borda fornece hoje. | <input type="checkbox">Acesso de usuários externos (usuários corporativos) <br/> <input type="checkbox">Acesso de usuário remoto (anônimo <br/>&nbsp;&nbsp; &nbsp; participantes da reunião externa) <br/> <input type="checkbox">Federação <br/> <input type="checkbox">Retransmissão de mídia | |
> | Qual dos seguintes recursos de chamada de voz você <br/>atualmente tem dependências? <br/>Observação de qualquer dependência adicional nos comentários <br/>coluna. | <input type="checkbox">Opções de ocupado <br/> <input type="checkbox">Estacionamento de chamadas <br/> <input type="checkbox">Recebimento de chamadas ou retirada de chamadas em grupo <br/> <input type="checkbox">Celulares comuns ou "divisão de mesa" <br/> <input type="checkbox">Grupos de respostas ou grupos de busca <br/> <input type="checkbox">Aparência da linha compartilhada <br/> <input type="checkbox">Linha particular <br/> <input type="checkbox">Caixa <br/> <input type="checkbox">Ligar via trabalho <br/> <input type="checkbox">Números de emergência ou informações <br/>&nbsp;&nbsp; &nbsp; (911, 811, 411) <br/> <input type="checkbox">Discagem de extensão <br/> <input type="checkbox">Atendedor automático <br/> <input type="checkbox">Acesso do assinante <br/> <input type="checkbox">Dispositivos analógicos <br/> <input type="checkbox">Fax <br/> <input type="checkbox">Mascaramento de identificação de chamadas ou alteração <br/> <input type="checkbox">Roteamento baseado em local <br/> <input type="checkbox">Roteamento de menor custo <br/> <input type="checkbox">Telefones do elevador | |

<a name="networking-and-access-to-microsoft-365-and-office-365-services"></a>Rede e acesso aos serviços do Microsoft 365 e do Office 365
---

Use a tabela a seguir para capturar os detalhes da rede da sua organização e como os usuários estão (ou serão) conectados ao Microsoft 365 e aos serviços do Office 365.

> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | Como fazer (ou quais serão) os usuários em escopo para a migração <br/>acessar o Microsoft Teams quando ele estiver no escritório? <br/>Selecione todas as opções que se aplicam. | <input type="checkbox">Conexão NAT roteada <br/> <input type="checkbox">Servidor proxy <br/> <input type="checkbox">Wi-Fi público <br/> <input type="checkbox">Wi-Fi gerenciado (não público) <br/> <input type="checkbox">ExpressRoute <br/>&nbsp;&nbsp; &nbsp; (Emparelhamento da Microsoft) ||
> | Se o acesso ao Microsoft 365 ou o Office 365 estiver por meio de uma<br/>servidor proxy, há alguma maneira de ignorar o proxy? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | A Rota Expressa está sendo usada atualmente? | <input type="checkbox">Sim <br/> <input type="checkbox">Não <br/> <input type="checkbox">Não, mas está sendo planejada | |
> | Você realizou uma avaliação de prontidão de rede? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Os usuários precisam usar uma VPN quando se conectam ao <br/>recursos corporativos remotamente? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Se for usada uma VPN, o tráfego do teams pode ser excluído do <br/>a VPN tem acesso direto aos serviços do Microsoft 365 e do Office 365? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Sua rede dá suporte a QoS? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Você pode priorizar o tráfego de áudio e vídeo das equipes <br/>para impulsionar uma experiência de alta qualidade? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Todos os locais dentro de uma região têm egresso na Internet, <br/>ou é um egresso na Internet centralizado para toda a região? | <input type="checkbox">Acesso regional à Internet <br/> <input type="checkbox">Acesso centralizado ao <br/>&nbsp;&nbsp; &nbsp; acesso à Internet | |

<a name="endpoints"></a>Pontos de extremidade
---

Use a tabela a seguir para capturar os detalhes dos clientes e pontos de extremidade em uso.

> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | Que sistema operacional de área de trabalho os usuários estão utilizando? | <input type="checkbox">Windows XP <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox">Mac (especifique a versão na coluna comentários). <br/> <input type="checkbox">Linux (especifica a distribuição na coluna comentários). <br/><input type="checkbox">Outros (Observe os detalhes na coluna comentários.) | |
> | Qual versão do Microsoft Office foi implantada <br/>para estes dispositivos? | <input type="checkbox">Office 2003 <br/> <input type="checkbox">Office 2007 <br/> <input type="checkbox">Office 2010 <br/> <input type="checkbox">Office 2013 <br/> <input type="checkbox">Office 2016 <br/> <input type="checkbox">Office para Mac 2011 <br/> <input type="checkbox">Office para Mac 2016 <br/> <input type="checkbox">Outros (Observe os detalhes na coluna comentários.) | |
> | Qual tecnologia de implantação do Office está em uso <br/>em sua organização? | <input type="checkbox">MSI <br/> <input type="checkbox">Clique para executar | |
> | Quais são os dispositivos móveis permitidos e compatíveis <br/>plataformas em uso? <br/>Selecione todas as opções que se aplicam. | <input type="checkbox">Windows <br/> <input type="checkbox">Celular <br/> <input type="checkbox">SS <br/> <input type="checkbox">Android <br/> <input type="checkbox">Outros (Observe os detalhes na coluna comentários.) | |
> | Como os dispositivos móveis são fornecidos? <br/>Selecione todas as opções que se aplicam. | <input type="checkbox">Dispositivos corporativos <br/> <input type="checkbox">Traga seu próprio dispositivo | |
> | Quais dispositivos os usuários usam atualmente para acessar <br/>serviços de voz e conferência <br/>(aparelhos de telefone, fones de ouvido, telefones, vídeo)? | | |

<a name="operations"></a>Operações
---

Use a tabela a seguir para capturar os detalhes dos aspectos operacionais do seu ambiente.

> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | Qual é o modelo de operações do Lync Server <br/>Skype for Business Server, implantação do Microsoft 365, <br/>ou a implantação do Office 365 hoje? | | |
> | Você pode estruturar a organização de suporte atual para <br/>Lync Server, Skype for Business Server, Microsoft 365, <br/>ou o Office 365? | | |
> | Se você estiver implantando em vários países ou regiões, <br/>cada país/região tem sua própria conta/telefonia <br/>pessoal para trabalhar ou isso será gerenciado centralmente? | <input type="checkbox">Suporte e operações regionais <br/> <input type="checkbox">Operações centralizadas e suporte | |
> | Você está acompanhando a Metodologia de Qualidade da Chamada? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Você atribuiu uma pessoa ou equipe ao <br/>Função de especialista em qualidade para a plataforma de colaboração <br/>em uso? | <input type="checkbox">Sim <br/> <input type="checkbox">Não ||
> | Como você monitora o Lync Server, Skype para <br/>Business Server, implantação do Microsoft 365 ou <br/>Implantação do Office 365? | | |
> | Você tem problemas de qualidade das chamadas? | <input type="checkbox">Sim<br/> <input type="checkbox">Não | |
> | Como e quando você fornece treinamento para seu <br/>assistência técnica sobre novos serviços e recursos? | | |

<a name="adoption-and-readiness"></a>Adoção e preparação
---

Use a tabela a seguir e registre o estado atual de adoção e preparação de sua organização.

>
> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | Qual é o seu uso ativo atual de <br/>Skype for Business? | **_ _** % total de usuários ativos versus usuários habilitados | |
> | Como a sua organização usa <br/>Skype for Business? | Conversas privadas <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> COMUNICAR <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Chamou <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Compartilhamento<br/> Reuniões <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Conferência<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Compartilhamento<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Chamou | |
> | Sua organização tem uma adoção do usuário <br/>e a equipe de gerenciamento de alterações? | <input type="checkbox">Sim<br/> <input type="checkbox">Não | |
> | Como você atualmente mede o sucesso do sucesso para a tecnologia <br/>distribuições como o Skype for Business? | | |
> | Qual a porcentagem de sua base de usuários que você diria <br/>adotou o Skype for Business? | | |
> | Qual é a opinião dos usuários a respeito do Skype for Business? | <input type="checkbox">Corretamente <br/> <input type="checkbox">Neutra <br/> <input type="checkbox">Mal | |
> | Qual das opções a seguir melhor descreve a distribuição <br/>estratégia usada para seu Skype for Business <br/>implementação? | <input type="checkbox">Grande alcance: campanha de E-mail com <br/>&nbsp;&nbsp; &nbsp; links para treinamento <br/> <input type="checkbox">Expandido: amplo alcance mais uma variedade <br/>&nbsp;&nbsp; &nbsp; campanhas de conscientização (cartazes, <br/>&nbsp;&nbsp; &nbsp; eventos, campeões) e treinamento <br/>&nbsp;&nbsp; &nbsp; (vídeos, guias do usuário, em pessoa) <br/> <input type="checkbox">Personalizado: expandido e mais direcionado <br/>&nbsp;&nbsp; &nbsp; mensagens e treinamentos por pessoa <br/> <input type="checkbox">Demais <br/>&nbsp;&nbsp; &nbsp; (Observe os detalhes na coluna comentários.) | |
