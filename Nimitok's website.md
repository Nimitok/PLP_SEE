import { Link } from 'react-router-dom'
import { useAuth } from '@/hooks/useAuth'
import { Button } from '@/components/ui/button'
import { Card, CardContent } from '@/components/ui/card'
import { ArrowRight, BookOpen, Briefcase, Mail, Star } from 'lucide-react'

const Index = () => {
  const { user } = useAuth()

  return (
    <div className="space-y-20">
      {/* Hero Section */}
      <section className="relative overflow-hidden bg-gradient-subtle">
        <div className="mx-auto max-w-7xl px-6 py-24 lg:px-8 lg:py-32">
          <div className="mx-auto max-w-2xl text-center">
            <h1 className="text-4xl font-bold tracking-tight sm:text-6xl">
              Welcome to My
              <span className="text-primary"> Digital Space</span>
            </h1>
            <p className="mt-6 text-lg leading-8 text-muted-foreground">
              A minimalist blog and portfolio where I share my thoughts, showcase my work, 
              and connect with like-minded individuals. Discover stories, projects, and insights.
            </p>
            <div className="mt-10 flex items-center justify-center gap-x-6">
              <Button asChild size="lg">
                <Link to="/blog">
                  Explore Blog
                  <ArrowRight className="ml-2 h-4 w-4" />
                </Link>
              </Button>
              <Button variant="outline" size="lg" asChild>
                <Link to="/portfolio">View Portfolio</Link>
              </Button>
            </div>
          </div>
        </div>
      </section>

      {/* Features Section */}
      <section className="mx-auto max-w-7xl px-6 lg:px-8">
        <div className="mx-auto max-w-2xl text-center">
          <h2 className="text-3xl font-bold tracking-tight sm:text-4xl">
            What You'll Find Here
          </h2>
          <p className="mt-4 text-lg text-muted-foreground">
            A curated collection of content designed to inspire and inform
          </p>
        </div>
        
        <div className="mx-auto mt-16 grid max-w-5xl grid-cols-1 gap-8 lg:grid-cols-3">
          <Card className="shadow-medium hover:shadow-large transition-shadow duration-300">
            <CardContent className="p-8 text-center">
              <div className="mx-auto flex h-12 w-12 items-center justify-center rounded-lg bg-primary/10">
                <BookOpen className="h-6 w-6 text-primary" />
              </div>
              <h3 className="mt-6 text-xl font-semibold">Thoughtful Writing</h3>
              <p className="mt-2 text-muted-foreground">
                In-depth articles on technology, design, and life lessons learned along the way.
              </p>
              <Button variant="ghost" asChild className="mt-4">
                <Link to="/blog">Read Posts</Link>
              </Button>
            </CardContent>
          </Card>

          <Card className="shadow-medium hover:shadow-large transition-shadow duration-300">
            <CardContent className="p-8 text-center">
              <div className="mx-auto flex h-12 w-12 items-center justify-center rounded-lg bg-primary/10">
                <Briefcase className="h-6 w-6 text-primary" />
              </div>
              <h3 className="mt-6 text-xl font-semibold">Creative Projects</h3>
              <p className="mt-2 text-muted-foreground">
                A showcase of selected works, experiments, and collaborations that define my journey.
              </p>
              <Button variant="ghost" asChild className="mt-4">
                <Link to="/portfolio">View Work</Link>
              </Button>
            </CardContent>
          </Card>

          <Card className="shadow-medium hover:shadow-large transition-shadow duration-300">
            <CardContent className="p-8 text-center">
              <div className="mx-auto flex h-12 w-12 items-center justify-center rounded-lg bg-primary/10">
                <Mail className="h-6 w-6 text-primary" />
              </div>
              <h3 className="mt-6 text-xl font-semibold">Let's Connect</h3>
              <p className="mt-2 text-muted-foreground">
                Have a question, idea, or just want to say hello? I'd love to hear from you.
              </p>
              <Button variant="ghost" asChild className="mt-4">
                <Link to="/contact">Get in Touch</Link>
              </Button>
            </CardContent>
          </Card>
        </div>
      </section>

      {/* CTA Section */}
      {!user && (
        <section className="bg-gradient-primary">
          <div className="mx-auto max-w-7xl px-6 py-16 lg:px-8">
            <div className="mx-auto max-w-2xl text-center">
              <h2 className="text-3xl font-bold tracking-tight text-primary-foreground sm:text-4xl">
                Join the Community
              </h2>
              <p className="mt-4 text-lg text-primary-foreground/80">
                Sign up to access exclusive content, comment on posts, and be part of the conversation.
              </p>
              <div className="mt-8">
                <Button 
                  size="lg" 
                  variant="secondary" 
                  asChild
                  className="bg-primary-foreground text-primary hover:bg-primary-foreground/90"
                >
                  <Link to="/auth">
                    <Star className="mr-2 h-4 w-4" />
                    Sign Up Now
                  </Link>
                </Button>
              </div>
            </div>
          </div>
        </section>
      )}
    </div>
  )
};

export default Index;
