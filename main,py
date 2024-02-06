from flask import Flask, render_template, request
import eventlet
from eventlet import wsgi

app = Flask(__name__)

@app.route('/embed')
def generate_embed():
    title = request.args.get('title', '')
    description = request.args.get('description', '')
    thumbnail = request.args.get('thumbnail', '')
    color = request.args.get('color', '')
    bigimg = request.args.get('bigimg', '').lower() == 'true'

    return render_template('embed.html', title=title, description=description, thumbnail=thumbnail, color=color, bigimg=bigimg)

if __name__ == '__main__':
    eventlet.wsgi.server(eventlet.listen(("0.0.0.0", 3524)), app)
