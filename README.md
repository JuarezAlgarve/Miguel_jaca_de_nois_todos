# site de apostas

from flask import Flask, render_template, request

app = Flask(__name__)

@app.route('/')
def index():
    return render_template('index.html')

@app.route('/apostas', methods=['POST'])
def apostas():
    valor_aposta = float(request.form['valor_aposta'])
    tipo_aposta = request.form['tipo_aposta']
    # Lógica para processar a aposta e retornar o resultado
    
    # Exemplo de retorno
    resultado = {
        'valor_aposta': valor_aposta,
        'tipo_aposta': tipo_aposta,
        'ganhou': True,
        'mensagem': 'Parabéns, você ganhou a aposta!'
    }
    
    return render_template('resultado.html', resultado=resultado)

if __name__ == '__main__':
    app.run()
