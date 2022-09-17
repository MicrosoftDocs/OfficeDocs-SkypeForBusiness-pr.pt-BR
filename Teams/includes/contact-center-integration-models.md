## <a name="integration-models-for-solution-providers"></a>Modelos de integração para provedores de soluções

<a name="steps"></a>

Como provedor de soluções do centro de contatos, há três modelos a serem escolhidos para integrar sua solução de central de contatos conectada ao Teams:

- Se você quiser usar SBCs certificados e Roteamento Direto para conectar uma solução do contact center ao Teams, consulte o [modelo conectar](?tabs=connect#steps).

- Se você quiser usar bots do Azure e as APIs de Comunicação do Microsoft Graph para permitir que os provedores de soluções criem aplicativos do Teams, consulte o [modelo Estender](?tabs=extend#steps).

- Se você quiser usar um SDK que permita que os provedores de soluções criem experiências nativas do Teams em seu aplicativo, consulte o [modelo do Power](?tabs=power#steps). As soluções de energia serão possíveis quando o SDK estiver disponível. Em breve.

### <a name="the-connect-model"></a>[**O modelo connect**](#tab/connect)

O modelo Connect usa SBCs certificados pela Microsoft e Roteamento Direto para conectar soluções do contact center à infraestrutura do sistema de telefonia do Teams, permitindo roteamento, configuração e insights do sistema aprimorados.

Os agentes podem configurar assistentes virtuais automatizados e filas de roteamento baseadas em habilidades para coletar informações e conectar clientes a especialistas no assunto.

**Destaques de recursos:**

Embora esses recursos não sejam uma lista abrangente de recursos para esse modelo de integração, as áreas de foco incluem:

- Office 365 autenticação para que os agentes se conectem ao locatário da Microsoft do cliente CCaaS integrado

- Ver quando os agentes estão disponíveis com o Teams

- Transferências e suporte a chamadas em grupo com o Teams

- APIs do Teams Graph e APIs de Comunicação na Nuvem para integração com o Teams

- Tronco SIP multilocatário para dar suporte a vários clientes no SBC do provedor de soluções.

- Provedores de solução para usar o [<span class="underline">controlador de borda de sessão certificado pela Microsoft (SBC)</span>](../direct-routing-border-controllers.md)

> [!NOTE]
> A solução de contato usada pelo agente não precisa de uma licença do sistema de telefonia. O usuário do Teams precisa de uma licença do sistema de telefonia e um número de telefone para a transferência de chamada do agente.

### <a name="the-extend-model"></a>[**O modelo Estender**](#tab/extend)

O modelo Estender integra-se ao cliente do Teams usando a plataforma de cliente [do Teams](/microsoftteams/platform/overview), [as APIs do Teams Graph](/graph/api/resources/teams-api-overview) e a [API de Comunicações na Nuvem no Microsoft Graph](/graph/api/resources/communications-api-overview). O modelo Estender também usa o sistema de telefonia do Teams para todas as chamadas do centro de contatos e experiências de controle de chamadas, e o provedor de soluções do centro de contatos atua como uma operadora de telefonia junto com o Microsoft 365.

Os agentes podem usar o Teams para colaboração interna e comunicação externa e podem se beneficiar de anotações contextuais dinâmicas correlacionando dados de vários sistemas antes de iniciar um compromisso e, em seguida, evitar a alternância de contexto dispendiante.

As organizações podem projetar fluxos de trabalho e configurações avançadas de roteamento até o indivíduo e medir a qualidade de seu sistema e interações.

**Destaques de recursos:**

Embora esses recursos não sejam uma lista abrangente de recursos para esse modelo de integração, as áreas de foco incluem:

- APIs do Teams Graph e APIs de Comunicação na Nuvem para integração com o Teams

- Aplicativo baseado em Equipes para experiências de agente

- Teams como o ponto de extremidade de chamada principal para os agentes

- Cliente do Teams chamando todos os controles de chamada

- Aplicativo de experiência do agente para o cliente Web e móvel do Teams

- Análise, gerenciamento de fluxo de trabalho, experiências baseadas em função para agentes no aplicativo CCaaS no Teams

- Experiências de chat e colaboração integradas aos clientes do Teams

- Preservar o desempenho e a qualidade das experiências de cliente do Teams em todos os aplicativos



### <a name="the-power-model"></a>[**O modelo de energia**](#tab/power)

O modelo de energia permite que os provedores de soluções criem aplicativos de voz nativos baseados no Azure usando a infraestrutura de chamada do Teams e a plataforma de cliente para fornecer soluções modernas e inteligentes para conexão colaborativa de cliente e agente. O objetivo do modelo do Power é fornecer uma experiência de centro de contato de um aplicativo com uma tela.


> [!NOTE]
> Em breve.
